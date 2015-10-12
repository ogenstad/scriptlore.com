---
layout: post
title: ErrorVariable, Parameter
#excerpt: "Probably the first thing you ever do whenever you learn a new language is to write your hello world program, however in PowerShell the most simple script will fail to load!"
modified: 2008-05-26
tags: [basics]
categories: powershell
---
<img align="left" src="{{ site.image_url }}/powershell-parameter-errorvariable.jpg" class="left" />
It is said that we learn from our mistakes, and that to improve learning it's best to write things down. How about storing our mistakes and errors in a variable? If that's not killing two flies with one stone, at least it's a useful feature of PowerShell. Let's use it and see how it works, using the Stop-Service cmdlet we try to stop a service: <!--more-->

{% highlight powershell %}
PS C:\> Stop-Service -name XAudioService -ErrorVariable myErrors
Stop-Service : Service 'XAudioService (XAudioService)' cannot be stopped due to the following error: Cannot open XAudio
Service service on computer '.'.
At line:1 char:13
+ Stop-Service  <<<
{% endhighlight %}

As you can see the error is also written to screen. From now on we can reference the error in the $myErrors variable we created:

{% highlight powershell %}
PS C:\> $myErrors
Stop-Service : Service 'XAudioService (XAudioService)' cannot be stopped due to the following error: Cannot open XAudio
Service service on computer '.'.
At line:1 char:13
+ Stop-Service  <<<
{% endhighlight %}

You might want to know that even if you don't specify the -ErrorVariable parameter all the errors will be storied in a special error called $error. Saving the error variable like we have done above will ensure that you have the last error saved. One thing you can do is to add a plus sign before the variable when you want to append to the error variable. Here is an example:

{% highlight powershell %}
PS C:\> Stop-Service -name XAudioService -ErrorVariable +myError
PS C:\> Stop-Service -name WinRM -ErrorVariable +myError
PS C:\> $myError.Count
2
PS C:\>
{% endhighlight %}
