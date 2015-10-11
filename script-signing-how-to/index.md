---
layout: page
title: Script Signing Guide
modified: 2015-10-11T20:53:07.573882-04:00
---
<h3>About the Series</h3>
With the introduction of PowerShell not paying attention to code signing means that in order to use scripting in PowerShell you have to make your system less secure than it is by default.

Because code signing and the whole pki thing can seem daunting perhaps you've just changed the <a href="http://scriptlore.com/powershell/execution-policy/">execution policy</a> and never looked back. With VBScript you didn't need to change anything on your system in order to run scripts so code signing was even less of an issue then.

This article series is aimed for those of you who want to swallow the red pill, and believe me it's not that bad. When you get into it PKI is actually quite fun. Regardless if you use VBScript, PowerShell or VBA this series should contain at least a few articles which should interest you if you want to learn more about code signing.

I will be covering some basic elements around PKI and guide you through an installation. In the best of worlds this would be done with at least two Servers. However if you don't want to start a committee I will explain how you can set up a simple, yet usable, CA environment using just free software.

You will see a few different scenarios. My intention is to sign most of the scripts here at ScriptLore. So you will also see how the PKI system for ScriptLore works.

My goal is that this will be an easy to follow guide, still if you have any questions don't hesitate to leave a comment or to contact me. Also if you have any suggestions for how the tutorial could be improved please let me know.

<h3>Articles in the Series</h3>
<ol>
	<li><a href="http://scriptlore.com/security/about-code-signing/">About Code Signing</a></li>
	<li>Security Benefits of Code Signing</li>
</ol>

<h3>Upcoming articles</h3>

As of yet this series isn't complete, there is more articles to come.
