---
layout: post
title: Stop writing for loops
---
##Use the native forEach function instead.

###Example:
{% highlight javascript %}

var numbers = [1,9,9,2];
for(var i = 0; i < numbers.length; i++) {
  console.log(numbers[i]);
}
// is equivalent to 
numbers.forEach(function(value, index, array) {
  /*via this callback function
    you still have access to the whole array
    and the index of the current value.*/
  console.log(value);
});
{% endhighlight %}
###Advantages:
1. `.forEach()` is easier to understand for somebody who is not a coder.
2. Faster to type for yourself.