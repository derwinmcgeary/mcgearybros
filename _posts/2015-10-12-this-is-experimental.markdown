---
layout: post
title:  "Almost Working!"
date:   2015-10-12 19:43:13
categories: blog
---

# Slowly configuring everything

This is now a bit better than it was. I guess
{% highlight r %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Take the mtcars data set and write up an analysis to answer their question using regression models and exploratory data analyses.

Your report must be:

Written as a PDF printout of a compiled (using knitr) R markdown document.
Brief. Roughly the equivalent of 2 pages or less for the main text. Supporting figures in an appendix can be included up to 5 total pages including the 2 for the main report. The appendix can only include figures.
Include a first paragraph executive summary.

# Motor Trend
This is a brief study of the difference in terms of fuel efficiency (measured in mpg) between vehicles with automatic and manual transmissions. In this study we found that Automatic is always better than Manual (where lower mpg is better).

## Executive Summary

## The Details
```{r echo=FALSE}
library(ggplot2)
data(mtcars)
mtcars$Transmission <- ifelse(mtcars$am == 0, "Automatic", "Manual")
mtcars$Transmission <- as.factor(mtcars$Transmission)
mtcars$wt <- mtcars$wt*1000
```
The following plot shows miles per gallon against wt, grouped by transmission for all the cars in our dataset. Higher is better.
```{r echo=FALSE}
plot1 <- ggplot(data=mtcars, aes(x=wt,y=mpg, colour=Transmission, shape=Transmission)) + geom_point() + geom_density2d()
plot1 <- plot1 + ylab("Fuel Efficiency (miles per gallon)") + xlab("Weight (lbs)")
plot1 <- plot1 + ggtitle("Fuel Efficiency")
plot1
```

### “Is an automatic or manual transmission better for MPG”
It certainly looks like manual transmissions have higher miles per gallon, but there is a compounding factor that manual transmissions also tend to be lighter. There is also the question of the number of cylinders.

### "Quantify the MPG difference between automatic and manual transmissions"
Well. Um. Yeah...

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
