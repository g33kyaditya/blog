---
title: '#28: GSoC with KDE Now – 6'
author: g33kyaditya
type: post
date: 2016-07-11T08:25:35+00:00
url: /?p=563
categories:
  - Uncategorized
tags:
  - gsoc16
  - kde

---
Hey ! I’m making KDE Now, an application for the Plasma Desktop. It would help the user see important stuff from his email, on a plasmoid. It’s similar to what Google Now does on Android. To know more, click [here][1]

&nbsp;

Another week has passed since I last posted about my progress. This week I did more work primarily on the plasmoid side of things.

I added receivers for the data, that was being thrown over D-Bus. To be a bit more precise, I exposed update signals over D-Bus which are emitted by the extractor plugins. There is a Datahandler that connects to these signals and calls the relevant method over D-Bus that I told you in my last post. Moreover, I made the whole daemon install as an autostart service. So every time, someone starts the plasmoid, it checks whether the daemon is running. If it&#8217;s not, then the daemon is started. This check, is made possible, by detecting whether the relevant interface is registered to D-Bus at the time.

Next up I exposed properties to be used by the cards. For example, properties like name, reservation number, or date. These will be binded to the User Interface elements in the cards. At the time, we hadn&#8217;t finalized the User Interface for the cards. So I skipped those and started writing the plasmoid&#8217;s backend. In essence, we instantiate a datahandler we wrote earlier. On receiving signals, we call relevant functions, which will instantiate a card, set it&#8217;s data and add the card to the current model.

For the next steps, I will write the User Interface for cards. Andres(Andy) Betts at the KDE-VDG was very helpful in providing me mockups for Event and Restaurant cards. I will start with them, and work on the other two, when they are finalized.

I&#8217;m good with my proposed timeline till now, but GSoC timeline doesn&#8217;t match well with the way most of our schools, here in India work. Hence, I plan to do as much as I can before school starts (which it has, already 🙁 ) . That should leave with with just a few more things to do until Final Evaluations.

 [1]: https://g33kyaditya.wordpress.com/2016/04/23/21-google-summer-of-code-2016/