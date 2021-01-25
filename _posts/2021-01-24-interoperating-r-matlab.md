---
layout: post
title:  interoperating R and MATLAB (TM)
date: 2021-01-24 05:50:00
description: an ultra-tiny tutorial with the R.matlab package
---

The [R.matlab](https://github.com/HenrikBengtsson/R.matlab) package,
created by [Henrik Bengtsson](https://github.com/HenrikBengtsson/), makes it effortless
to interoperate between R and MATLAB.

Before starting, make sure to add the MATLAB binary to your ``PATH``.
In macintosh computers running shells such as ``bash`` or ``zsh``, that can be done as:

```
export PATH="/Applications/MATLAB_R2017a.app/bin:$PATH"
```

Within an R session, we can create a MATLAB server as follows:

{% highlight R %}

library(R.matlab)
Matlab$startServer(port=9942)

{% endhighlight %}

From another R session, the client, we can request a connection to the server by doing:

{% highlight R %}

library(R.matlab)
matlab <- Matlab(port=9942)
open(matlab)

{% endhighlight %}

The instruction ``open(matlab)`` should return ``TRUE`` in case the connection was succesfull.

Now, we can use MATLAB at our disposal from the client R session. For example, let's set the value
of a MATLAB variable which we will denote by ``x`` and let's query that value:

{% highlight R %}

setVariable(matlab, x = 1)
y <- getVariable(matlab, "x")

{% endhighlight %}

The variable ``y`` is a list object that contains, among other things, the value of the variable we requested:

{% highlight R %}

y$x

{% endhighlight %}

We can also evaluate MATLAB expressions:

{% highlight R %}

evaluate(matlab, "z = 41 + 1;")
zz <- getVariable(matlab, "z")

{% endhighlight %}

And many more, like reading/writing MAT files, executing scripts/functions, and so on :)

If that's useful for you, be sure to check out the [API reference](https://cran.r-project.org/web/packages/R.matlab/R.matlab.pdf) of R.matlab.