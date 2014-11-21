---
layout: post
title: "Code sharing inside an institution and beyond"
description: "How to collaborate on codes"
category: programming
tags: [programming, git]
---
{% include JB/setup %}

## Starting a project
A couple of weeks ago, two of my colleagues and I decided to write a piece of
software that would act like a wrapper for another software that is more
tedious and annoying to use. We knew this would be a big project, so we created
a repository on GitHub for the purpose. We realized that this project could not
only have a great impact on our group here at the institution, but also for the
general community working on the same problems as we (spectral analysis of
stars).

Personally I was very excited, since this gave me an opportunity to take my
Python programming skills to the next level, after being stuck at the same
place for some time now. Also it would make my future life easier, and give me
more time to do science and not code development.

We added small functions to the program when we had time. To be honest we
didn't have much time to work on this, but I was still sure (still am)
that this would be a good project.

Earlier this week I asked one of the collaborators for a meeting to discuss
some issues. And that is when I found out...

## Sharing code internally
My colleague told me that his previous supervisor (he is mine and the last
colleagues' supervisor currently) already have most of this written in Python
and ready to use, which he have done for some time now. I was speechless! First
I thought that was amazing, since the project have the potential as we realized
earlier. Second, I was not able to understand why this was not shared amongst
people in our group.

I asked that question to my colleague, which I assumed he would also have
asked. The reply he got was simply

> You did not ask me for it.

This is not a fair response at all. We had no idea this code already
existed, and we can't go around asking everyone in the building before we want
to make a program, if it is already written. This code should have been shared!
No questions asked in my opinion. At least amongst the rest of the institution.

### What else is out there?
After my frustration gradually went away I asked the simple question.

> How much code is out there, that I have also written in either a better or
> worse way?

In either case, that seems like a waste of time to me. Why should two, three,
four people write the same software just because we did not share our code?
Maybe that development time could have been used to improve the already written
software or on science (which we are actually hired to do).

Unfortunately I have a feeling that there is a lot of software out
there, that is not shared. Probably many big codes are shared, since it
is "easy" to write an article around it and get the credit it deserves.
I think that the problem is with smaller pieces of software, either
simple scripts or wrappers. If the code is big or small, it was created for a
purpose. There is a high probability that other people can benefit from that
purpose, and thus it should be made public.

Note that I use public rather vague. I say public in two different ways.

    1. Public for the rest of the people working at an institution (not really
    public).
    2. Public for everyone. Everyone should be free to use the code an improve
    upon it.


## Where should we put our codes?
Obviously as GitHub is hosting my blog I'm biased toward that. However, the
idea of having code online with version control seems to me as a good choice. I
will focus now on GitHub since that is what I know how to use.

Here you can create two type of users

    1. Free user with all repositories public for all.
    2. Payed user with a number of repositories closed, and only open for some
    invited users.

I have a free user (it is possible to upgrade), and recently I started a
[repository](https://github.com/DanielAndreasen/astro_scripts) with some of my
scripts. This is maybe not the most elegant solution, but it is a solution. If
you have bigger codes (and not just a bunch of scripts) this should have its
own repository. One of the advantages of using a site like GitHub is that
people can contribute to the code available easily. Another is the possibility
for making a wiki and/or a dedicated web page for the repository.

An alternative to a page like GitHub many uses is a personal web page.
This is in principle okay, but it lacks the advantages of a dedicated
web page for code development. There is no version control, no issue
tracker, and no easy opportunity for combined development.

### License
Last of all, you should always use a license for your code. This is not
simething I have been very good at, but I see the advantage if you want to have
certain rights.

If you, as I am, new to the code sharing world and picking the right license,
[this site](http://choosealicense.com/) might help you

Now, there is only to start share your codes so we can all benefits from it and
start doing more fantastic science! Also, if anyone have comments on sharing
code in an institution I am very interested in that.
