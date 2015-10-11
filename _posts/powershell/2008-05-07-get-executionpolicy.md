---
layout: post
title: Get-ExecutionPolicy
#excerpt: "Probably the first thing you ever do whenever you learn a new language is to write your hello world program, however in PowerShell the most simple script will fail to load!"
modified: 2008-05-01
tags: [basics, cmdlet, security]
categories: powershell
---
<img align="left" src="{{ site.image_url }}/cmdlet-get-executionpolicy.jpg" class="left" />
PowerShell uses for different settings called [Execution Policy](http://scriptlore.com/powershell/execution-policy/) which governs how scripts will run on your computer and if they need to be digitally signed. Get-ExecutionPolicy is a Cmdlet which allows you to view which Execution Policy that is currently used by your computer. <!--more-->

### SYNTAX
Get-ExecutionPolicy

* [-Verbose](http://scriptlore.com/powershell/verbose/)
* [-Debug](http://scriptlore.com/powershell/debug/)
* [-ErrorAction](http://scriptlore.com/powershell/erroraction/)
* [-ErrorVariable](http://scriptlore.com/powershell/errorvariable/)
* [-OutVariable](http://scriptlore.com/powershell/outvariable/)

### Examples

{% highlight powershell %}
PS C:\> Get-ExecutionPolicy
Restricted
{% endhighlight %}
