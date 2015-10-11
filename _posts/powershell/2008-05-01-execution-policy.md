---
layout: post
title: Concerning Execution Policy
excerpt: "Probably the first thing you ever do whenever you learn a new language is to write your hello world program, however in PowerShell the most simple script will fail to load!"
modified: 2008-05-01
tags: [basics, security]
categories: powershell
---
<img align="left" src="{{ site.image_url }}/execution-policy.jpg" alt="Execution Policy" class="left" />
Probably the first thing you ever do whenever you learn a new language is to write your [hello world program](http://scriptlore.com/about/hello-world/), however in PowerShell the most simple script will fail to load! Instead of the friendly greeting PowerShell will spit back: <!--more-->"hello.ps1 cannot be loaded because the execution of scripts is disabled on this system."

The error is fairly straight forward though, the Execution Policy governs whether you are able to run scripts or not. If you want to run scripts at all you have to change the execution policy.

### Unrestricted
<img align="left" src="{{ site.image_url }}/execution-policy-unrestricted.jpg" alt="Unrestricted" class="left" />
Unrestricted is the careless cowboy setting. If you set the Execution Policy to Unrestricted PowerShell will run any script regardless if it has a digital signature or not. As you might have guessed this is the worst setting in terms of security. Some things are fun to do in the short term, but you never know what kind of troubles you face down the road.

### RemoteSigned
<img align="left" src="{{ site.image_url }}/execution-policy-remotesigned.jpg" class="left" />
Using the RemoteSigned Execution Policy means that PowerShell will require that scripts downloaded from the Internet are signed by a trusted source. However you won't have to signed scripts stored locally on your machine. This is a great setting if you just want to learn some scripting and take PowerShell for a test drive and don't want to dive into the script signing business. Besides, you can always get your PKI environment up tomorrow.

### AllSigned
<img align="left" src="{{ site.image_url }}/execution-policy-allsigned.jpg" class="left" />
The AllSigned policy requires every script you want to run to be signed by a trusted certificate, if you want to run scripts this is the setting which will let your sysadmin sleep soundly at night. In order to run your scripts you will have to get some [script signing](http://scriptlore.com/script-signing-how-to/) procedures in place.

### Restricted
<img align="left" src="{{ site.image_url }}/execution-policy-restricted.jpg" class="left" />
The Restricted option means that PowerShell will not run any script at all not even if it is digitally signed. You might be thinking that this would make PowerShell quite worthless as a scripting language, and you might be right. However PowerShell is also a shell and you can use it without ever writing a single script. Restricted is the default Execution Policy which is why your scripts won’t run when you start using PowerShell. In order to be able to run scripts you have to change the Execution Policy.

### Changing the Execution Policy
You can change the Execution Policy with the Set-ExecutionPolicy cmdlet, to view your current Execution Policy you can use the [Get-ExecutionPolicy](http://scriptlore.com/powershell/get-executionpolicy/) cmdlet.
