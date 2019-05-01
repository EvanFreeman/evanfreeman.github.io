---
layout: post
title: Don't set the state if an old promise resolves. 
---

Easy way to make sure you don’t set the state if an old promise resolves when the prop changes or the component unmounts.

{% highlight javascript %}
const [someState, setSomeState] = useState(null);
useEffect(() => {
  let current = true;
  fetchSomething(someProp).then(result => {
    if(current) {
      setSomeState(result)
    }
  })
  return () => { current = false }
}, [someProp])
{% endhighlight %}
