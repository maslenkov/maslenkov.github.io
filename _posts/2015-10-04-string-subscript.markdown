---
layout: post
title:  "String#subscript"
date:   2015-10-04 22:41:00
categories: ruby
---

This is a cool ruby feature to find substring.

{% highlight ruby %}
# [] - works like `match` method, but return substring, not #<MatchData "...">
'string'[/str/] #=> "str"
# The real benefit you get when you find part of substring
'string'[/s(t)r/, 1] #=> "t"
'string'.match(/s(r)r/)[1]
#=>
# NoMethodError: undefined method `[]' for nil:NilClass
#   from (irb):3

# And the coolest thing that it can be used without tmp variables
'string'[/s(r)r/, 1] #=> nil
{% endhighlight %}

And real live code example

{% highlight ruby %}
#get country code from the phone
'+12345678901'[/+(.*)\d{10}/, 1]
{% endhighlight %}

Of course there are not all abilities of String#[] method. And you should be confident with using nil as returned value. So check out the [Ruby docs][ruby-docs] for more info. Or RubyTaps #99.

[ruby-docs]: http://ruby-doc.org/core-2.2.3/String.html#method-i-5B-5D
