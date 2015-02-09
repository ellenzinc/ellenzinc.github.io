---
layout: post
title: Latex Cheatsheet for Paper Writer
data: 2015-02-09
---

<p>Here are some tips for writing papers and it is constantly updated. </p>

<h2>Customizing Enumerated Lists</h2>

<p>Very often, you would want to change the counters for
<span style="font-family:monospace; color:#2020C0">
enumerate
</span>
environment in latex. One way to achieve this is to use
<span style="font-family:monospace; color:#2020C0">
enumitem
</span> package.
</p>



<p>
However, if you are using the IEEE template with <span style="font-family:monospace; color:#2020C0">
\documentclass[]{IEEEtran}
</span>, you might well faw an error 
<span style="font-family:monospace; color:#2020C0">
Command \labelindent already defined.
</span>
This is because both the <span style="font-family:monospace; color:#2020C0">
IEEEclass.cls
</span>
document class and the <span style="font-family:monospace; color:#2020C0">
enumitem.sty
</span>
package define the macro 
<span style="font-family:monospace; color:#2020C0">
\labelindent
</span>.

Therefore, before including the <span style="font-family:monospace; color:#2020C0">
enumitem
</span> package, you can disable the <span style="font-family:monospace; color:#2020C0">
\labelindent
</span> using:
{% highlight latex %}
\let\labelindent\relax
\usepackage{enumeitem}
{% endhighlight %}

 
</p>

<p> After successfully including the enumitem, you can customize your enumeration counter using the following code
{% highlight latex %}
\begin{enumerate}[label=Type-\arabic*:]
\item Item 1
\item Item 2
\item Item 3
\end{enumerate}
{% endhighlight %}

</p>

<p>
Here, the counter is "Type-1", "Type-2",...
</p>

<p>
Besides \arabic*, it also supports a series of starred versions of \alph, \Alph, \roman, \Roman as counters for the current level enumeration.
</p>

<p>
By default, <span style="font-family:monospace; color:#2020C0"> align=right</span>, which means that if you are setting a very long counter including texts, it can be out of the range of text.

In terms of final appearances, <span style="font-family:monospace; color:#2020C0">
align=left 
</span>  is recommended, since it leave some space at the beginning for a neater listing.
However, this may not be of your desire when you are writing a paper that is currently marginally passing the page limit. To save space, while not violating the page margin, you can use
{% highlight tex %}
leftmargin=*
{% endhighlight %}
If you are still not happy with the result, you can customize the leftmargin yourself using 
{% highlight tex %}
leftmargin=2cm
{% endhighlight %}
</p>
