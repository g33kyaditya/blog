---
title: '#5 : Dual Boot Windows 8(8.1) with Linux'
author: g33kyaditya
type: post
date: 2014-11-06T15:19:32+00:00
url: /?p=18
categories:
  - Uncategorized

---
In the last PULUG session they taught us how to Dual Boot Windows with Linux. Still, I see many of my classmates messing up their systems. One of them had to do a clean installation of Mint 17 (Cinnamon) after literally destroying both his Windows and Mint bootloaders. Ofcourse, he lost all his movies. We were in much despair.

I myself have been dualbooting since I was in Grade 8. No big deal! (is it ?). But that is only till you have Windows 7. Windows 8 and 8.1 that come pre-installed with laptops complicates matters (to a great extent). We lost the movies because of it. 🙁

I myself am running a DualBoot of Windows 7 with an Ubuntu LTS. I had a Windows 7 Ultimate so it was a fairly simple task for me. Just the regular BIOS.

So, lets dig in. But not without some theory. (You can skip this part if you don&#8217;t want to go through the crappy details)

\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\_____

Windows 8 and 8.1 that come pre-loaded with laptops have replaced BIOS with UEFI. This is where the problem lies. UEFI has a &#8220;securemode&#8221; that doesn&#8217;t let us tinker with the bootloader. And even if it does, we won&#8217;t be able to boot through Grub if its not digitally signed into UEFI. And guess what !! It is not. That means we&#8217;ll have to find a way around this.

&#8220;**Unified Extensible Firmware Interface** (UEFI) is a specification for a software program that connects a computer&#8217;s firmware to its operating system (OS). UEFI is expected to eventually replace BIOS.&#8221;

It was originally meant as a security tweak to avoid any potential malware.

\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\_____

Pre-requisites :

&#8211; A Linux Image (.iso) [Whatever flavour you like. I personally like Ubuntu]

&#8211; A compatible laptop/desktop

&#8211; A pen drive (atleast 2 GB)

&#8211; Linux Live USB Creator (LiLi) or Universal USB Installer

Step 1 :

Before starting anything, just to be safe , create a backup of all your important data .

Step 2 :

Create a live USB disk. Fire up LiLi or Universal USB Installer (whatever you have). Select the .iso image and make a live disk.

Step 3:

Make some space for your fresh installation (depending on your need). Make sure not to use the C partition for your distro. It will erase your Windows.

To make a partition in Windows 8, go to Disk Management tool. You can find disk management tool by searching for ‘disk’ in Control Panel.

[<img class="alignnone size-medium wp-image-19" src="https://g33kyaditya.files.wordpress.com/2014/11/disk_partition.jpeg?w=300" alt="disk_partition" width="300" height="210" />][1]

In the Disk Management tool, right click on the drive which you want to partition and select **shrink volume**. Shrink the volumes to free up space.You can leave the free space as it is. We shall use it while installing Ubuntu.

Step 4 :

Disable fast startup for Windows. It&#8217;s optional. But it would be better to have it disabled.

Go to **Control Panel** > **Hardware and Sound** > **Power Options** > **System Settings** > **Choose what the power buttons do** and uncheck the **Turn on fast startup box**.

Step 5 :

Disable Secureboot. This is the most important step. The new **secure boot** feature of Windows 8, originally intended for security feature for rootkit viruses, prevents dual booting of Windows with Linux. To dual boot Windows 8 with Linux, we must disable secure boot in UEFI.

&#8211; Open the settings charms in Windows by pressing **Windows+I** keys. At the bottom, you’ll see the option of **Change PC settings**. Click on it.

[<img class="alignnone size-medium wp-image-20" src="https://g33kyaditya.files.wordpress.com/2014/11/disable_secure_boot_1.jpeg?w=300" alt="Disable_Secure_Boot_1" width="300" height="136" />][2]

&#8211; There will be a slight difference in PC settings for Windows 8 and Windows 8.1. Depending upon which one you are using, you can follow the respective procedure described below:

**Windows 8:** In Windows 8, you need to go to General PC settings and select **Advanced startup** and then click on **Restart now**

**[<img class="alignnone size-medium wp-image-21" src="https://g33kyaditya.files.wordpress.com/2014/11/change_pc_settings_windows8.jpg?w=300" alt="Change_PC_Settings_Windows8" width="300" height="200" />][3]**

**Window 8.1:** In Windows 8.1, go to **Update and recovery** from left sidebar. [<img class="alignnone size-medium wp-image-22" src="https://g33kyaditya.files.wordpress.com/2014/11/disable_secure_boot_windows8_2.jpeg?w=300" alt="Disable_Secure_Boot_Windows8_2" width="300" height="168" />][4]

Then click **Restart now** under **Advanced Startup**

[<img class="alignnone size-medium wp-image-24" src="https://g33kyaditya.files.wordpress.com/2014/11/disable_secure_boot_windows8_31.jpeg?w=300" alt="Disable_Secure_Boot_Windows8_3" width="300" height="168" />][5]

&#8211; After you have clicked Restart now button, you will be presented with some options to choose from in the next screen. Select **Troubleshoot** here

[<img class="alignnone size-medium wp-image-25" src="https://g33kyaditya.files.wordpress.com/2014/11/troubleshoot_windows8.jpg?w=300" alt="Troubleshoot_Windows8" width="300" height="200" />][6]

&#8211; In **Troubleshoot** menu, select **Advanced options**

&#8211; In Advanced options menu, choose **UEFI Firmware settings**

[<img class="alignnone size-medium wp-image-26" src="https://g33kyaditya.files.wordpress.com/2014/11/troubleshoot_windows8_2.jpg?w=300" alt="Troubleshoot_Windows8_2" width="300" height="200" />][7]

&#8211; Next, click on **Restart** button to reboot your system in UEFI settings.

&#8211; By this time you must have been booted in to UEFI utility. You can change various settings here but all we want to do right now is to disable secure boot option to allow dual booting of Ubuntu or any other Linux

Move to Boot tab, there you’ll find **Secure Boot** option which is set to enabled. Use the arrow key to go to Secure Boot option and then press **enter** to select it. **Use + or – to change its value**. Confirm it when prompted. Press **F10 to save the changes** and exit the UEFI settings.

[<img class="alignnone size-medium wp-image-27" src="https://g33kyaditya.files.wordpress.com/2014/11/disable_secure_boot_windows8.jpg?w=300" alt="Disable_Secure_Boot_Windows8" width="300" height="225" />][8]

Step 6 :

Once you have disabled secure boot, it’s time to install your distro. Plug in the USB and boot the system from it. To boot from USB, will have to choose boot from USB option from within Windows itself. Either with PC Setting (like for UEFI) or pressing shift key while clicking on Restart.

Step 7 :

Once you have booted in the live USB, you will be presented with option to try or install Ubuntu. Click on install. You will be presented with few screen options to choose the language. It will then do some checks on available space, power and internet connection etc. Just click on **Continue**.

[<img class="alignnone size-medium wp-image-28" src="https://g33kyaditya.files.wordpress.com/2014/11/installing_windows8_ubuntu.jpeg?w=300" alt="Installing_Windows8_Ubuntu" width="300" height="171" />][9]

Step 8 :

Now in the **Installation Type**, select **Something Else**.

Step 9 :

Remember we had created some free space beforehand? We shall use the free space to create Root, Swap and Home. Select the free space and click on the + sign. However its a matter of personal choice. If you have 8GB of RAM, you don&#8217;t need the swap space. Else, I strongly suggest you to create it, equal to the RAM you have. Also, you can have everything on your Root directory like me. Here&#8217;s a comparison.

You can have only one single partiton (C) in which your Windows Installation resides along with your data such as Music,Downloads etc. This is what happens when you create a single Root (/) Directory.

OR

In Windows you can have a separate partitions. One for the Windows Installation (C) and others for your data like Videos, Movies etc. This is what happens when you create different partitions for Root(/) and Home Directory. The Linux Installation resides in Root and your data goes into Home.

Step 10 :

Depending on your choice you can either put everything in one partiton or have different partitions for Root and Home. If you chose the latter, the Root Partition could be anything between 10-20 GB. Other Space can be used for your Home.

In any case, select the Mount Point according to your need.

/ : For Root Partition

[<img class="alignnone size-medium wp-image-29" src="https://g33kyaditya.files.wordpress.com/2014/11/installing_windows8_ubuntu_3.png?w=300" alt="Installing_Windows8_Ubuntu_3" width="300" height="196" />][10]

/home : For home Partition

[<img class="alignnone size-medium wp-image-30" src="https://g33kyaditya.files.wordpress.com/2014/11/installing_windows8_ubuntu_5.png?w=300" alt="Installing_Windows8_Ubuntu_5" width="300" height="196" />][11]

If you need a swap space, then select it equal to the amount of RAM you have. (Optional for those with 8GB of RAM)

[<img class="alignnone size-medium wp-image-31" src="https://g33kyaditya.files.wordpress.com/2014/11/installing_windows8_ubuntu_4.png?w=300" alt="Installing_Windows8_Ubuntu_4" width="300" height="173" />][12]

Well, you have almost won the battle. You can smell victory now. Next you will be asked to set username password etc. Basically, you just need to click next now. Select all the details.

And Voila ! You now have a Linux Distro alongside Windows 8. Tested with Ubuntu 14.04. Will work with other distros as well.

That&#8217;s all for now.

Thanks for Reading

 [1]: https://g33kyaditya.files.wordpress.com/2014/11/disk_partition.jpeg
 [2]: https://g33kyaditya.files.wordpress.com/2014/11/disable_secure_boot_1.jpeg
 [3]: https://g33kyaditya.files.wordpress.com/2014/11/change_pc_settings_windows8.jpg
 [4]: https://g33kyaditya.files.wordpress.com/2014/11/disable_secure_boot_windows8_2.jpeg
 [5]: https://g33kyaditya.files.wordpress.com/2014/11/disable_secure_boot_windows8_31.jpeg
 [6]: https://g33kyaditya.files.wordpress.com/2014/11/troubleshoot_windows8.jpg
 [7]: https://g33kyaditya.files.wordpress.com/2014/11/troubleshoot_windows8_2.jpg
 [8]: https://g33kyaditya.files.wordpress.com/2014/11/disable_secure_boot_windows8.jpg
 [9]: https://g33kyaditya.files.wordpress.com/2014/11/installing_windows8_ubuntu.jpeg
 [10]: https://g33kyaditya.files.wordpress.com/2014/11/installing_windows8_ubuntu_3.png
 [11]: https://g33kyaditya.files.wordpress.com/2014/11/installing_windows8_ubuntu_5.png
 [12]: https://g33kyaditya.files.wordpress.com/2014/11/installing_windows8_ubuntu_4.png