---
layout: post  
title: Sending AirMail email to DevonThink  
---  
I spend a lot of my day managing email and so selecting a good email programme is therefore very important. Over the years I have mostly used Apple Mail but more recently I have been drawn to the power of [AirMail](http://airmailapp.com) by Bloop Software. AirMail ticks most of the buttons of what I want in an email programme, such as reminders, deferring email, markdown composing and integration with a range of other programmes. But one thing that I really wanted to be able to do was to integrate Airmail with DevonThink. My preferred workflow is to triage my email, decide on the course of action required, i.e. reply immediately, defer until later, trash or place in my task list for action. Part of the workflow also involves placing a copy of the email and any associated attachments in my project management structure managed by DevonThink. My project structure, which is created from a DevonThink template, typically looks like this: 

![Project structure in DevonThink]({{ site.url }}/images/projectstructure.png)

The failing of AirMail has been the difficulty in automating the export of email to DevonThink. However, AirMail has some rudimentary AppleScript support and the following scripts now enable me to export email and attachments to DevonThink. I have attached the applescripts to an Alfred workflow and call the workflow with a keyboard shortcut thus automating the process with a minimum of keystrokes.

**Applescript to send mail message from AirMail to DevonThink**  
{% highlight applescript %}
(*
name:           	Save mail message
description:	Use as a script to save mail message from Airmail to DevonThink
author:	Kyle Eggleton www.eggleton.co.nz
*)
Subject: " & theSubject & "
From: " & theSender & "
Date: 
MIME-Version: 1.0
Content-Type: text/html; charset=\"iso-8859-1\"


" & theSource
{% endhighlight %}

**AppleScript to send attachments from AirMail to DevonThink**  

{% highlight applescript %}
(*
name:           	Save attachments
description:	Use as a script in Airmail rules to save attachments to the selected folder.
author:		Kyle Eggleton www.eggleton.co.nz
*)
{% endhighlight %}