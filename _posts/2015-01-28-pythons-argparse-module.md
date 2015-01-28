---
layout: post
title: "Python's argparse module"
description: "Bring your scripting to the next level"
category: programming
tags: [programming, python, scripting]
---
{% include JB/setup %}

## Scripts the wrong way
[argparse](https://docs.python.org/3/library/argparse.html) is my new favorite
python module. Python is a very nice language for making scripts (or Command
Line Interfaces, CLI), and argparse helps with this task.

So here is the setup. We want to write a small script that can do some work for
us. It will take some input arguments when called from the command line. How
will we do this? Many of us are guilty of writing something like this

{% highlight python %}
import sys

if len(sys.argv) != 4:
    print 'Script takes 3 arguments'
    raise SystemExit

a, b, c = sys.argv[1:]
print a + b + c
{% endhighlight %}

Remember that the first argument of `sys.argv` is the name of the script
itself. The example above is very simple, but imaging if your script
is somewhat more complicated. 2 months after you wrote it, you need to
use it again, but have no idea how it works. You need to go back and
read the comments (which you always should write), and maybe even the
source code. This is a waste of time and tedious when you just need
the script. How awesome could it be to write something like `python
script.py -h` and a help text will be printed? Well, that is one of the
things argparse does for you!

## argparse
argparse can do a lot of things for you, and I am no expert, but I know the
basics, and that is already orders of magnitude better than `sys.argv`
solutions. Here is how it works.

{% highlight python %}
import argparse

parser = argparse.ArgumentParser(description='Description of your program')
parser.add_argument('num1', help='First number in the sum', type=float)
parser.add_argument('num2', help='Second number in the sum', type=float)
parser.add_argument('num3', help='Third number in the sum', type=float)
parser.add_argument('-s', '--sign', help='Positive (default) for sum, negative for difference',
                    type=int, default=1)
args = parser.parse_args()
if args.sign > 0:
    print args.num1 + args.num2 + args.num3
else:
    print args.num1 - args.num2 - args.num3

{% endhighlight %}

This code is longer than the `sys.argv` example, but it also does a lot
more. It generates a help text, have error handling if the type of an argument
is invalid, and can set both required and optional arguments. Let's try to run
above in the shell

{% highlight bash %}
python script.py

usage: script.py [-h] [-s SIGN] num1 num2 num3
script.py: error: too few arguments
{% endhighlight %}

So we learn we have too few arguments, which is right. In the construction we
have required the three numbers to be provided. Let's try run it with the `-h`
flag.

{% highlight bash %}
python script.py -h

usage: script.py [-h] [-s SIGN] num1 num2 num3

Description of your program

positional arguments:
  num1                  First number in the sum
  num2                  Second number in the sum
  num3                  Third number in the sum

optional arguments:
  -h, --help            show this help message and exit
  -s SIGN, --sign SIGN  Positive (default) for sum, negative for difference
{% endhighlight %}

If you are not convinced by now, then just stay with me for two more examples.

### Example 1 - testing the script
Now we will try to give it something to work with. We want our program to
calculate the difference between three numbers, and then the sum.

{% highlight bash %}
python script.py 42 21 7.3 -s -1

13.7
python script.py 42 21 7.3

70.3
{% endhighlight %}

It seems our program is working. Now, let's try to crash it.

### Example 2 - crashing the script
Our program don't know how to add strings, so, funny as we are, let's give it
some strings to work with.

{% highlight bash %}
python script.py 13 hello world

usage: script.py [-h] [-s SIGN] num1 num2 num3
script.py: error: argument num2: invalid float value: 'hello'
{% endhighlight %}

Awesome, it gives an error message we can understand. If we corrected the
error, it will complain about the `num3` argument in the same way. What if we
only give 2 arguments?

{% highlight bash %}
python script.py 20 22

usage: script.py [-h] [-s SIGN] num1 num2 num3
script.py: error: too few arguments
{% endhighlight %}

Yet another error we can understand and easily correct. This happens because we
specified the `type` in the script, and the 3 numbers are "positional
arguments" which means we have to provide this.


## Conclusion
There are other modules out there like argparse, all of them better than
`sys.argv`, so stop using that solutions. Then your script will be much easier
to use in 2 weeks, 2 months, maybe even years after you wrote them. And even
better, if you
[share](http://danielandreasen.github.io/:about/2014/11/21/code-sharing-inside-an-institution-and-beyond/)
your code other can easily use and understand them. So take the time to write a
good help text and description, then you will forever thank the past-you for
doing so.

For more realistic examples, I've put some of my favorite scripts on GitHub.
Feel free to use them at any time. The repository can be found
[here](https://github.com/DanielAndreasen/astro_scripts).
