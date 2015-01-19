---
layout: post
title: "Creating masks in python"
description: "How to pick data from an array"
category: programming
tags: [programming, python, numpy]
---
{% include JB/setup %}

## Masks in python

When working with data arrays masks can be extremely useful. Masks
are an array of boolean values for which a condition is met (examples
below). These boolean arrays are then used to sort in the original data
array (say we only want values above a given value). Here we will use
[numpy](http://numpy.org) arrays which are especially good for handling
data.

First thing first, let's create some random data.

{% highlight python %}
import numpy as np

data = np.random.random(10)
print data

[ 0.75969243,  0.89605676,  0.2667259 ,  0.70995589,  0.37337853,
  0.99088484,  0.09859641,  0.11185514,  0.11283875,  0.69043097]
{% endhighlight %}

We now have 10 random numbers between 0 and 1 to work with.

## Higher than mask
Now we create a mask for all values higher than 0.5 and print the values

{% highlight python %}
mask1 = data > 0.5
print data[mask1]

[ 0.75969243  0.89605676  0.70995589  0.99088484  0.69043097]
{% endhighlight %}

To be complete here is how the mask looks like

{% highlight python %}
print mask1

[ True  True False  True False  True False False False  True]
{% endhighlight %}

With other words, the mask is just an boolean array according to the condition
given above (values higher than 0.5).

## Lower than mask
It is hopefully no surprise that similar masks can be created for values
lower than 0.5 in a very similar way

{% highlight python %}
mask2 = data < 0.5
print data[mask2]

[ 0.2667259   0.37337853  0.09859641  0.11185514  0.11283875]
{% endhighlight %}


## Other operations
We are not limited to greater-than and lower-than operators. Others such as
`==` (equality), `!=` (not-equality), `<=` (less-than or equal), and so on.

## Combining masks
Before we combine masks we must first understand the difference between `and`
and `or`. These two statements combine two booleans and return a single
boolean. Here is a table to better understand what is going on.

| bool1   | bool2  | `and`  | `or`  |
| ------- | ------ | ------ | ----- |
| True    | True   | True   | True  |
| True    | False  | False  | True  |
| False   | True   | False  | True  |
| False   | False  | False  | False |

The first two columns shows the booleans we use, and the two next columns shows
the return from `and` and `or`, respectively. We want to use this with out
numpy arrays, but they use a slightly different syntax. Instead of `and` we
will use `&`, and instead of `or` we will use `|`.

### Values between a range
Now we want all values in the range [0.2, 0.8].

{% highlight python %}
mask3 = (data > 0.2) & (data < 0.8)
print mask3

[ True False  True  True  True False False False False  True]
print data[mask3]

[ 0.75969243  0.2667259   0.70995589  0.37337853  0.69043097]
{% endhighlight %}

### Values outside a range
Now we want all values from our array outside of the above range. This can be
done in two easy ways.

First let me show the same approach as the above example.

{% highlight python %}
mask4 = (data < 0.2) | (data > 0.8)
print mask4

[False  True False False False  True  True  True  True False]
print data[mask4]

[ 0.89605676  0.99088484  0.09859641  0.11185514  0.11283875]
{% endhighlight %}

Note that when creating this mask the less-than and greater-than sign
have changed place, and the operator is no longer a `&` but a `|`.

The easiest way however is using `mask3` directly like this.

{% highlight python %}
print ~mask3

[False  True False False False  True  True  True  True False]

print data[~mask3]
[ 0.89605676  0.99088484  0.09859641  0.11185514  0.11283875]
{% endhighlight %}

The `~` sign simply change all the values in the mask to the opposite, and
hence we get the same result.

If you have any questions or comments about masks feel free to leave
them in the comment section down below.
