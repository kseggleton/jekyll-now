---
layout: post
title: Airmail iOS to DevonThink
---
I am not stuck in front of my computer all day. In fact half the time I take my iPad with me and try and try and do as much as I can in iOS. I have struggled until recently to find a way in which to file emails into DevonThink-to-go (DTTG). However, in the latest release of DTTG to 2.1.3 the URL scheme has received a massive up-date including the ability to generate HTML documents and PDF documents (the later through Base 64 encoding). By creating a custom action in Airmail it is now possible to send an HTML formatted email through to DTTG. One issue though is that in my archived emails in DevonThink I like to have a link back to the original email and the senders details. The following URL scheme, triggered as a custom action in AirMail, will do just that.

{% highlight text %}  
x-devonthink://x-callback-url/createhtml?title=[message_subject]&location=[message_linkback]&source=%3Cp%3E%3Cstrong%3EFrom%3A%3C%2Fstrong%3E%20%3Ca%20href%3D%22mailto%3A[message_sender]%22%3E[message_sender_name]%3C%2Fa%3E%3Cbr%2F%3E%0A%3Cstrong%3ESubject%3A%3C%2Fstrong%3E%20[message_subject]%3Cbr%2F%3E%0A%3Cstrong%3E%3C%2Fp%3E%0A%0A%3Cp%3E[message_html]%3C%2Fp%3E&x-success=airmail://  
{% endhighlight %}

The URL scheme look a little complicated but it is simply URL encoded HTML. The first portion creates an href (i.e. an HTML link), which when selected will create an email back to the sender. The second portion is the subject. The final portion is the message itself as HTML with an x-success back to AirMail. A URL link, located in the info box in DTTG, is made back to the original email. The formatted email will look something like:



> **From:** [Xanthe Squidgery](example.com)  
> **Subject:** Intergalactic meeting of moon miners  
>
> Message to all moon miners....