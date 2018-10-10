---
title: '#31: GSoC with KDE Now – 9'
author: g33kyaditya
type: post
date: 2016-08-15T18:05:16+00:00
url: /?p=674
categories:
  - Uncategorized
tags:
  - gsoc16
  - kde

---
Hey ! I’m making KDE Now, an application for the Plasma Desktop. It would help the user see important stuff from his email, on a plasmoid. It’s similar to what Google Now does on Android. To know more, click [here][1].

&nbsp;

Roughly three weeks have passed since I last blogged about my project. School started and it was tough finding time for everything let alone blogging. This year&#8217;s Summer of Code is reaching it&#8217;s end and I have much to talk about this time around. In the end I also have a surprise for you.

&nbsp;

To start with, I worked on the Database I talked about earlier. Now all plugins save their maps into a Sqlite database and when the daemon runs, it finds these maps and prepares to load it into a card. There&#8217;s a catch here though, as I will have to pass the maps over to D-Bus and there are synchronizations issues. There&#8217;s still  a way to solve it but that involves editing an auto generated xml file manually. We wish to avoid this manual editing however, for easy maintenance in future. This might be some bug in the Qt based parsing/generation tool I use. But I need to still figure this out with my mentor.

Since I had worked on all the points I had proposed, my mentor asked me to add support for more than one email account. So, now you can add multiple accounts to KDE Now and the daemon will fetch emails from all those accounts.

I also worked on the credentials input mechanism. It has improved largely since I last blogged. Now the user is presented with a kind of form when KDE Now is started for the first time. You will be required to add your email credentials in the form. It adds your data to KWallet and the daemon retrieves it later.

Finally, have a look at the demo below.

{{< youtube a5bJdDuQRIQ >}}

As soon as the application logs into your account, it fetches all emails within a span of one month and if it finds an email of Event, Flight, Hotel or Restaurant reservation that confirms to the schemas of Google Now, a card will appear. In the later part of the video, I have shown you how KDE Now works when an email arrives and a new card is generated dynamically with that information. I send raw html much like how a vendor sends to you.

&nbsp;

I will add another blog post regarding my final project report in a couple of days so be on the lookout.

PS: I&#8217;m still looking for a graphics designer familiar with svg for KDE Now. If you are interested in helping me, drop a comment below with your contact details. Don&#8217;t worry your contact details will be kept private, as I monitor all comments before publishing.

That&#8217;s all folks. Cheers !

 [1]: https://g33kyaditya.wordpress.com/2016/04/23/21-google-summer-of-code-2016/