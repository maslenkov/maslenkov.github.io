---
layout: post
title:  "String#subscript"
date:   2015-10-04 22:41:00
categories: ruby
---

{% highlight ruby %}
'string'[/str/] #=> "str"
'string'[/s(t)r/, 1] #=> "t"
'string'.match(/s(r)r/)[1]
#=>
# NoMethodError: undefined method `[]' for nil:NilClass
#   from (irb):3
'string'[/s(r)r/, 1] #=> nil
{% endhighlight %}

Check out the [Ruby docs][ruby-docs] for more info.

[ruby-docs]: http://ruby-doc.org/core-2.2.3/String.html#method-i-5B-5D
