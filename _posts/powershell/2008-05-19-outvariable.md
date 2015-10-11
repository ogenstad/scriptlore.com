---
layout: post
title: OutVariable, Parameter
#excerpt: "Probably the first thing you ever do whenever you learn a new language is to write your hello world program, however in PowerShell the most simple script will fail to load!"
modified: 2008-05-19
tags: [basics, cmdlet, security]
categories: powershell
---
<img align="left" src="{{ site.image_url }}/powershell-parameter-outvariable.jpg" class="left" />
Building on the Perl motto; "There's more than one way to do it", PowerShell lovers will tell you that they can play too. Basically the -OutVariable parameter stores the output from a cmdlet to a variable and at the same time letting the cmdlet display all the output to the screen. For example looking at the Get-ChildItem cmdlet you can store the output in a variable by doing:
<!--more-->
{% highlight powershell %}
$myChildren = Get-ChildItem
{% endhighlight %}

Using the -OutVariable parameter you would instead type:
{% highlight powershell %}
Get-ChildItem -OutVariable myChildren
{% endhighlight %}

This would also store the output in the myChildren variable (notice the lack of the $ sign), but unlike the first example the output would be printed to the screen. This might sound a lot like the Tee-Object cmdlet. However you can also use OutVariable like this:
{% highlight powershell %}
Get-ChildItem Directory1 -OutVariable myChildren
Get-ChildItem Directory2 -OutVariable +myChildren
{% endhighlight %}

This way the $myChildren variable would hold the contents of both Directory1 and Directory2. Another difference, if you're in a hurry and want to juice out some performance, can be shown by the Measure-Command cmdlet.
{% highlight powershell %}
Measure-Command {Get-ChildItem | Tee-Object -variable myTeeOutput}
TotalMilliseconds : 3,3151
{% endhighlight %}
{% highlight powershell %}
Measure-Command {Get-ChildItem -OutVariable myOutVariableOutput}
TotalMilliseconds : 2,0668
{% endhighlight %}

Folks, we have a winner! But what will we do with all the extra free time? If you just want to store the variable and not display the output you can use the Out-Null cmdlet:
{% highlight powershell %}
Get-ChildItem -OutVariable myChildren | Out-Null
{% endhighlight %}
