---
layout: page
title: Why learn to script?
modified: 2015-10-11T20:53:07.573882-04:00
---
So you don’t know any scripting language and you’re not sure if you want to spend the time learning it? If you’re reading this you’ve at least probably thought of learning your first language. Working in the IT industry you’re used to contently having to update your skills. Whether it’s Linux or Windows there’s always a new version or system to learn. Scripting fits outside this cycle, either you know it or you don’t. You probably are able to do most of your work without writing a line of script code and with all the other information you have to dig through and learn why would you spend the extra time with scripting?

### 1 - Automation
Scripts can be a great help when it comes to automating repetitive (read boring) tasks. Take the example from Life of Brian, when he is tasked with writing “Romans go home” one hundred times on the wall. It took the poor fellow all night and he was exhausted, did he get any appreciation? No he was chased away by a centurion. Just compare working an all-nighter with doing the same in PowerShell, it’s a one-liner:

{% highlight powershell %}
for ($i = 0; $i -lt 100; $i++) { write-host "Romani Ite Domum" }
{% endhighlight %}

If the above seems hard to understand, keep this in mind; At the most it would take 15 minutes to explain that line in detail. Compared to working all night it’s still quite a good deal, right?

### 2 - Only Human
Working from the above example working all night is tiring, Brian could have easily made a mistake and forgot a character or a word no big deal on the wall paintings but if you’re doing something repetitive chances are you won’t do it exactly the same way every time. I think Agent Smith says it best;

>  Never send a human to do a machine’s job.

Doing something once is easy enough, following instructions most people can perform all kinds of complicated tasks. However if you’re going to do the same task several times over and over again I see two things happening. Your brain will be under stimulated and bored, the workdays will seem longer and you will enjoy your work less every time you perform the task. The second part is that you will start introducing errors like in a Chinese whispers game, after you’ve done a task 100 times chances are that not all of the sequences have the same result.

However a computer doesn’t get bored and doesn’t introduce errors by mistake, if you’ve written a script which can perform a task once it can perform the same task a hundred times.

### 3 – Speed
Most tasks you can perform with a computer would run faster if the you part was removed, i.e. when the computer has to wait for your input the job is going to take much longer compared to when the computer does all the work.

An example of this is if you install Windows XP from a vanilla CD, there are countless steps where the computer has to wait for your input before it can continue. If you use an unattend.txt file most of these choices can be pre-programmed which speeds up the installation, other deployment options are faster still.

Though it might tie in a bit with automation, if you can speed things up with scripts it means you get either more time to work on other tasks or more spare time to practice your cooking skills!

### 4 – It Provides Lasting Value

If you've spent the entire day wading through logs or creating user accounts, at the end of the day you can say that you've gone through x thousands of log entries or you've created y user accounts. Your rewards for the day might include sore eyes and shoulders and perhaps a wish you had some better coffee at the office.

Coming back to work the next day you can start over again, you feel a bit better since today it isn't Monday anymore.

However if instead you'd spent the day writing a script to do the task you've created a specialized worker who does one thing and does it well without getting bored or sore.  Even though your script might take longer than a day to write once you have it you can save so much time, since you performed the tasks manually before you've basically created a low paid worker.

### 5 – It's not as difficult as you might think

Even though you might feel dizzy just by the thought of seeing some script code, you have to realize that it's actually easier that you might think. Imagine you're looking at an advanced mathematical formula left on a blackboard in a university. Provided you haven't studied mathematics you might just shake your head and leave it to academics. What you need to do is to break it down to pieces you can understand, there's no need for you to start off by trying to decipher what the code does.

Starting from the beginning with math we all know what 3+5 if, with scripting it really doesn't have to be more advanced than that. Just learning the very basics will enable to you write scripts which can accomplish a great deal. Once you've mastered the basics you might run into a problem for which you have to learn how something new works. After a while it all will become more natural to you, when you're at this stage you'll regret not learning earlier.
