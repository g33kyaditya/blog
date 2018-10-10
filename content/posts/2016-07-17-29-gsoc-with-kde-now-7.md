---
title: '#29: GSoC with KDE Now – 7'
author: g33kyaditya
type: post
date: 2016-07-17T17:39:10+00:00
url: /?p=606
categories:
  - Uncategorized
tags:
  - gsoc16
  - kde

---
Hey ! I’m making KDE Now, an application for the Plasma Desktop. It would help the user see important stuff from his email, on a plasmoid. It’s similar to what Google Now does on Android. To know more, click [here][1]

&nbsp;

Another week has passed. And I&#8217;m back with more updates of what I&#8217;ve done over last week. I worked on the plasmoid side of things this time. Andres(Andy) Betts at the KDE-VDG was very generous and had given me some nice mockups for Event and Hotel cards.

I wrote the UI of these two cards based on the mockups I got. It was all in QML and went like a breeze. Next up, I worked on the plasmoid to make sure, that the cards get loaded dynamically in the correct way. It was an earlier commit but I figured out, it was not completely correct.

I also made some improvements on the daemon side of things. Mainly, devised a way to load the extractor plugins just once and set different map data. Earlier the plugins were getting loaded every time an update over email was received. My debugging skills were put to test, trying to find this one out. Along with some Database issues, I&#8217;m facing while the daemon is started by the plasmoid (over D-Bus). These two bugs coupled together were not letting the cards generate. I haven&#8217;t yet made the Database fix yet but that&#8217;s because it is low on my priority list. Also, some things are going in my mind regarding it, so I&#8217;ll rather postpone it.

Finally, a working model is ready. Well sort of. Not for the end user. But for the developer. Checkout the screenshots &#8211;

&nbsp;

&nbsp;

There are two cards here, Event and the Hotel Card. Both of them were dynamically generated from test emails. The first one (Hotel Card) was generated on the plasmoid, after I pinned the plasmoid to the desktop. The lower one (Event Card) was generated after I sent another test email, while the plasmoid was still on the desktop. This one utilised the IDLE feature of the IMAP client daemon FTW !

Things look good from here. Well I must say, I got a morale boost when I saw those cards &#8220;magically&#8221; generating for the first time. You see, I&#8217;ve been working for this a long time. And all I could see was just the debug output of the daemon. While that is informative and all, but that is not what I intended in the first place. Seeing the results made me very happy and I guess I even announced it on an IRC channel XD

For the next part, I&#8217;ll be working on Flight and Restaurant cards. Now I don&#8217;t have mockups for those. But I know they&#8217;ll be along the lines of what we have right now. It could take me sometime though, to come up and finalize the UI for them. Also, I have to find a way to get the user details. I&#8217;ve been testing with hard-coded values. But this has to change ofcourse.

Thanks for reading.

See you later !

 [1]: https://g33kyaditya.wordpress.com/2016/04/23/21-google-summer-of-code-2016/