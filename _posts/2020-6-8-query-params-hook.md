---
layout: post
title: React router hook for easier access to query parameters. 
description: A simple hook that makes parsing and accessing the query parameters a bit easier. 
---

To access the query parameters in react router you have to first access the
location, then the search property. Then you need to parse out the query
parameters from the resulting string. Though this isn't that hard it gets
repetative, and there are many solutions to this issue. But most of them are
a bit more involved than I wanted so I wrote this hook to simpligy it a bit. 

{% highlight javascript %}
import { useLocation } from 'react-router-dom';

const useQueryParams = () => {
  const location = useLocation();
  const search = location.search;
  if (!search) return {};

  const queryParams = search.slice(1).split('&');
  return queryParams.reduce(result, param => {
    const values = param.split('=');
    result[values[0] = values[1];
    return result;
  }, {});
};
{% endhighlight %}


