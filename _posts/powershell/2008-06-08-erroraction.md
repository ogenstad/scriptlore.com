---
layout: post
title: ErrorAction, Parameter
#excerpt: "Probably the first thing you ever do whenever you learn a new language is to write your hello world program, however in PowerShell the most simple script will fail to load!"
modified: 2008-06-08
tags: [basics]
categories: powershell
---
<img align="left" src="{{ site.image_url }}/powershell-parameter-erroraction.jpg" class="left" />
Like many other aspects of PowerShell, -ErrorAction kind of explains itself when you think of it. Basically it instructs PowerShell what action to take when an error occurs. The actions you can set are Continue (which is default), Stop, SilentlyContinue and Inquire. Let's take a look.<!--more-->

### Continue
You can verify that Continue is the default action by looking at the $ErrorActionPreference variable. We'll be using the Stop-Process Cmdlet to test this.

{% highlight powershell %}
PS C:\> $ErrorActionPreference
Continue
PS C:\> Stop-Process 206,304
Stop-Process : Cannot find a process with the process identifier 206.
At line:1 char:13
+ Stop-Process  <<<< 206,304
Stop-Process : Cannot find a process with the process identifier 304.
At line:1 char:13
+ Stop-Process  <<<
{% endhighlight %}
Since we know continue is the default error action we don't need to use "-ErrorAction Continue".

### Stop

The Stop error action instructs PowerShell to stop executing after the first error.

{% highlight powershell %}
PS C:\> Stop-Process 206,304 -ErrorAction Stop
Stop-Process : Command execution stopped because the shell variable "ErrorActionPreference" is set to Stop: Cannot find
 a process with the process identifier 206.
At line:1 char:13
+ Stop-Process  <<<
{% endhighlight %}

Compared to when we used "Continue", PowerShell will only try to stop the process with id 206 and never move on to 304 since it failed to stop the first one.

### SilentlyContinue

As you might guess SilentlyContinue acts like Continue with the exception that we don't see the errors. To save some typing we don't need to write out ErrorAction, we can use EA for short.

{% highlight powershell %}
PS C:> Stop-Process 206,304 -EA SilentlyContinue
PS C:\>
{% endhighlight %}

### Inquire

Inquire informs us that there has been an error and lets us decide what to do.

{% highlight powershell %}
PS C:\> Stop-Process 206,304 -EA Inquire

Confirm
Cannot find a process with the process identifier 206.
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): h
Stop-Process : Command execution stopped because the user selected the Halt option.
At line:1 char:13
+ Stop-Process  <<<
{% endhighlight %}
