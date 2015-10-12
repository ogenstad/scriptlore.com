---
layout: post
title: About Code Signing
#excerpt: "Probably the first thing you ever do whenever you learn a new language is to write your hello world program, however in PowerShell the most simple script will fail to load!"
modified: 2009-02-24
tags: [basics]
categories: security
---
<img align="left" src="{{ site.image_url }}/i_love_you.jpg" class="left" />
There was a lot of love going around in May 2000, but as they say love hurts. If organizations would have had some code signing routines in place, the ILOVEYOU virus would have been killed in its crib. Of course those hippie days are long gone as no one tends to allow .vbs files in the mail server or if it's not blocked there the email client should block it. However code signing can do more than just avoiding the mitigating click, still in this post I won't focus on the security benefits of code signing.
<!--more-->
### What is code signing (the short version)?

Code signing is a mechanism where we use public key certificates to sign our code or scripts. What the process does is to add a portion to the file, which can be verified against the certificate which signed it. Why we would want to do this leads us to the next subject.

### Goals of Code Signing

In short there are two goals with code signing; **Authenticity** and **Integrity**. When a script is digitally signed we can look at the signature and find out which digital certificate was used in order to sign the script. Let's say we work with Bob, we would very much like to use one of the scripts he has written but based on past experience we don't want to run any scripts from our other coworkers. If Bob has signed the scripts he has created we can look at the signature and verify that the code is authentic. I.e. the script has actually been written by Bob and not by the hotshot whose last script crashed the server. The second goal is that of integrity, what it means is that the script is still intact or complete. We want to make sure that nothing in the script has changed since Bob signed the script, if it has the script signature has lost its integrity. So if someone were to edit Bob's script it will fail its integrity check when we validate the script signature. As long as we are able to validate the signature we know that the file was indeed signed by Bob, or technically by Bob's certificate.

### Bonus Goal - Non-Repudiation

The two other goals work in favor for Bob, if something has changed in the code he can just say that the certificate validation failed and at that point he can't be held accountable for what the modified code does. However if the signature is intact and something goes wrong when we run the script Bob can't repudiate the fact that he was the one who wrote the script.

### Conclusion

In a situation where we trust another party, the goals of code signing is to verify that the scripts or code we are about to run are created by a person we trust and that they haven't been modified.
<br />
<br />
*This post is part of the series [How to Implement Code Signing for Scripters](http://scriptlore.com/script-signing-how-to/)*
