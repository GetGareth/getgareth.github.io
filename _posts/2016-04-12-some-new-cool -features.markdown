---
layout: post
author: Jasper Sprengers -> <a href="http://twitter.com/jsprengers" target="_blank">@jsprengers</a>
---

About regex, matching glue lines, dashboards and specification of duration: During the last <a href="http://twitter.com/codecentric_nl" target="_blank">@codecentric_nl</a> DevThursday we had the chance to add some great new functionality to the Gareth framework. From now on you will be able to use regular expressions (and re-use code for different experiments) and we made it easier and more flexible to specify the duration of experiments.


# Matching glue lines to definition methods

Your baselines, assumptions, success and failure definitions need to correspond to Java methods that do the actual work.
These Java methods reside in so-called definition classes that are known to Gareth through configuration, and the relevant methods are identified through the @Baseline, @Assume, @Time, @Success and @Failure annotations. In its simplest form, it looks like this:


Baseline: sale of anvils
{% highlight ruby %}
@Baseline(glueLine = "sale of anvils")
 public void getSaleOfAnvils() {
 System.out.println("Getting sale of anvils");
}
{% endhighlight %}

or with using the built-in Storage:

{% highlight ruby %}
@Baseline(glueLine = "sale of anvils")
public void getSaleOfAnvils(final Storage storage) {
  storage.store(product, dbase.getCurrentSalesOfProduct("anvil"));
}
{% endhighlight %}

A shortcoming of this approach is that there is a strict one-to-one mapping between glue line and definition method. If you want to get the sale of hammers or screwdrivers in a different experiment you'd need to write new methods for each with probably very similar code. That hardly seems efficient. It would be much better if we could make our method configurable by adding the product as a parameter:
public void getSaleByProductCode(final String productCode){...}

Then we can indicate the configurable part in the glue line by means of a grouped regular expression, like so:
{% highlight ruby %}
@Baseline(glueLine = "sale of (.*?)")
public void getSaleOfProductByCode(final Storage storage,final String productCode) {
  storage.store(product, dbase.getCurrentSalesOfProduct(productCode));
}
{% endhighlight %}
Multiple groupings are allowed:

{% highlight ruby %}
@Success(glueLine = "order (\\d{1,3}) (.*?) from (.*?)")
public void sendTreats(int amount, String treat, String supplier) {
	String.format("Enjoy the %d %s from %s", amount, treat, supplier);
}
{% endhighlight %}
And this lets you re-use the same Java code for very different glue lines:
Success: order 3 carrot cakes from local bakery
Success: order 5 iPhones from Amazon

It's a powerful mechanism, but there are some rules to the game:

* The number of parenthesised regex groups must be exactly equal to the number of parameters in the method, ignoring the optional Storage parameter, which always comes first and is injected by Gareth when specified. The values are then extracted from the glueline and the definition method is called with these parameters:
"order 3 carrot cakes from local bakery" matches on 3, "carrot cakes" and "local bakery" and calls sendTreats(3,"carrot cakes","local bakery")

* Permitted arguments types are String, Integer, Long, Double and their corresponding primitive types. Use of other types in definition methods will cause an error. Gareth must be able to convert parse the regex matches (always String) to a valid Java type.

# Specifying duration
The regex mechanism as described above is not available for the Time glue line, meaning that the @Time annotated definition method cannot be configured with arguments. However, you may leave it out entirely if your Time glue line follows the pattern of [number] [duration], where duration is one of second, minute, hour, day, week, month, year, or their corresponding plurals:
* Time: 48 hours
* Time: 3 weeks
* Time: 42 days
* Time: 1 month
* Time: 1 year

Note that month is always 30 days and year is 365 days. Running the experiment with 1 month duration on the 1st of February will check the assumption on the 3rd of March, ignoring leap years. If you want specific behaviour you can still write your own implementation:
{% highlight ruby %}
Time: Tuesday after next Easter
@Time(glueLine = "Tuesday after next Easter")
public Duration sampleTime() { .. }
{% endhighlight %}

<hr>
# Dashboard
Also we upgraded the dashboard quite a bit so there is a quick overview of running experiments and the amount of failing/succeeding:
<img src="{{ site.baseurl }}/images/blogpics/pie.png" class="fit image">

And for a more detailed view of the experiments:
<img src="{{ site.baseurl }}/images/blogpics/list.png" class="fit image">

Do you like it or do you need some help with setting Gareth up? Do you want to contribute in any way? Please let us know!
