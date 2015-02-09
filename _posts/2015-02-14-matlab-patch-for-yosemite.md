---
layout: post
title: "Patch Your MatLab for MAC Yosemite"
date: 2015-2-14
---

<p>Are you feeling excited about the brand new OS X Yosemite? Yeah, me too. But I delayed my update until recently due to notorious "Matlab does not open in MAC OS bug".</p>

<p>
While the bug is fixed for R2014b, following the instruction here can save your past installation of 2011a &mdash; swiftly in 10 minutes.
</p>

What you need is a patch  <a href="https://www.mathworks.com/support/bugreports/1098655"> R20xxx_patch_1098655.dmg </a> for your corresponding matlab version. Following the instruction, you will be able to open the MATLAB. 

If you are using a MAC pro with retina display as I do, you might feel the text on MATLAB is blurry.

While there are many solutions you can find. 
The following one seems to be quick one.
<ol>
<li> Install the latest JRE from <a href= "www.http://www.java.com/en/download/mac_download.jsp">www.java.com </a></li>
<li> Open up your terminal and type the following command:
    {% highlight bash %}
$cd /Applications/MATLAB_R2014a.app/sys/java/jre/maci64
$mv jre/ jre.orig
$ln -s /Library/Internet\ Plug-Ins/JavaAppletPlugin.plugin/Contents/Home/ jre
    {% endhighlight %}
</li>
</ol>

Re-start your Matlab app and you are all set.


