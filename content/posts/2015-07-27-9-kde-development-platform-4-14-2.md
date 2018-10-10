---
title: '#9 : KDE Development Platform 4.14.2'
author: g33kyaditya
type: post
date: 2015-07-27T15:07:30+00:00
url: /?p=56
categories:
  - Uncategorized

---
So here I am as promised. As I write this, I am sitting in my hostel room. One of my friends is playing GTA V. The other is copying GTA V. One is watching Game of Thrones and one is just lying around. And here I am writing this. \*Slow claps please :)\*

KDE Development Platform :

> The KDE Development Platform consists of an integrated set of technologies that help you build applications quickly and efficiently.

The KDE Development Platform is a way for the application KDE Developers to distribute the workload. The source becomes easy to maintain and write. Consistency and Stability is improved.

So a few days back, I find myself trying to solve a bug, a Junior Job on Amarok. The Podcast Directory was **according to the bug **wasn&#8217;t showing anything. Generally, there&#8217;s a list of Directories like this. Take a look.

[<img class="alignnone size-medium wp-image-57" src="https://g33kyaditya.files.wordpress.com/2015/07/snapshot1.png?w=300" alt="snapshot1" width="300" height="169" />][1]

Now as usual, my first step was to reproduce to the bug. I compiled the source and spent more than a day to do it. But everything was working fine on my build. I went to the IRC. Found out that I had an older version of KDE Development Platform 4.13.3 The newer version was perhaps breaking something. I had to have the newer version.

I spent a weekend trying to update it.

    sudo add-apt-repository ppa:kubuntu-ppa/backports
    sudo apt-get update 
    sudo apt-get upgrade  
    

As you might already know, I am running KDE on Unity. Since I don&#8217;t get automatic updates for KDE, things were a mess. The above commands didn&#8217;t seem to work. Still, the KDE Development Platform was 4.13.3 I did some digging and did a

     sudo apt-get dist-upgrade

This gave me a bunch of output. That showed, that the libraries of some applications were already at 4.14.2 What the hell is that ?  I spent one more day trying to find some work around.

Did a

    sudo apt-get -f install 

It made all the libraries at Platform 4.13.3

Again ran

     sudo apt-get dist-upgrade

It worked this time. The KDE Development Platform is 4.14.2

\*Happy :)\*

Still, I can see the Podcast Directories in Amarok. Time to bug some developers at the IRC. Will update if I find something interesting.

Thanks for Reading

 [1]: https://g33kyaditya.files.wordpress.com/2015/07/snapshot1.png