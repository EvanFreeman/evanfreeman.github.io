---
layout: post
title: Filtering falsy values
---

How to quickly discard falsy values from an array? Thanks to
Array.filter(Boolean), this is an easy task. 

{% highlight javascript %}
> ['this', 'has', undefined, 
  false, 0, null, NaN, 'values'].filter(Boolean)

[ 'this', 'has', 'values' ]
{% endhighlight %}

This works because Boolean(val) is a function that coerces a value into a Boolean.
