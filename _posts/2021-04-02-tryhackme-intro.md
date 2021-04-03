---
layout: post
title: Getting Started With TryHackMe
---


<div class="message">
  Howdy! This blog post shows step-by-step instructions on how to get started on the website TryHackMe. TryHackMe is a free way to learn and practice cyber security hands on skills. The paid version gives you access to their in-browser Kali Linux machine as well as focuses learning paths.
</div>

To get started, navigate to <a href="https://tryhackme.com">TryHackMe</a>. Here you can make a new account. If you don't have a Kali Linux machine setup, it may be worth purchasing the TryHackMe membership. This will give you access to their in browser Kali Linux machine. For the purpose of this walkthrough, I assume that you have previously setup a Kali Linux virtual machine, and that you will be using it for all TryHackMe challenges. 

Once you have created your new account it should ask your experience level, why you want to use TryHackMe, and to choose a learning path. For this walkthrough, we will choose the **Complete Beginner** path. 

![placeholder](/img/tryhackme/complete-beginner.png "Complete Beginner path")

As you can see this learning path will introduces all of the following:
- Linux basics
- Web application security
- Network security
- Scripting challenges
- Privilege Escalation

Each learning path consists of several *rooms*. These are the individual learning modules that present you with tasks, as well as provide you with the vulnerable machines. To be able to use the machines that are vulnerable in each *room*, we first have to connect to TryHackMe's network. The **Complete Beginner Introduction** rooms introduce how to do this. 

![placeholder](/img/tryhackme/complete-beginner-introduction.png "Complete Beginner Introduction")

Click on the room **Tutorial** so we can get started!

## Tutorial

To connect to TryHackMe's network we have to connect using OpenVPN. Make sure you open up the <a href="https://tryhackme.com/room/tutorial">Tutorial Room</a> in the browser of your Kali Linux virtual machine. This way when we download something it will be stored in the virtual machine rather then your host machine. 

Hit the start machine button that the arrow points to.

![placeholder](/img/tryhackme/starting-your-first-machine.png "Starting Your First Machine")

This button will be a constant across all rooms. This is what starts the vulnerable machine that you will be hacking. You should see the following new bar appear.

![placeholder](/img/tryhackme/machine-status.png "Active Machine Information")

The title of the machine will vary from room to room. After some time the IP address should appear. This is the local IP address of the vulnerable machine for this room. You will only be able to reach this IP address if you have connected to TryHackMe's network. To do this we will be using OpenVPN in our Kali Linux virtual machine.

### OpenVPN

To connect your VM (virtual machine) to TryHackMe's network we are going to use OpenVPN. To get started open up a terminal and type the following to update your machine.

```console
  foo@bar:~$ sudo apt update && sudo apt upgrade
```

Allow this to finish. After, install the OpenVPN package using

```console
foo@bar:~$ sudo apt install openvpn
```


Now that we have OpenVPN installed, we need to get our configuration file from TryHackMe. Navigate to their page explaining connecting via <a href="https://tryhackme.com/access?o=vpn">OpenVPN</a>. After changing your region to your preference, click the button that says *Download My Configuration File*. 

![placeholder](/img/tryhackme/openvpn-access-details.png "OpenVPN Access Details")

Now that the file is downloaded, we can open a terminal and connect using the following command

```console
foo@bar:~$ sudo openvpn /path/to/config_file
```

Replace */path/to/config_file* with the location of the downloaded configuration file. If you ran this command correctly, you should see that your IP address is not long 0.0.0.0 in the *OpenVPN Access Details* pane. This is now your local IP address in TryHackMe's network.

### Finishing the Tutorial

Now back at the <a href="https://tryhackme.com/room/tutorial">Tutorial Room</a> you should see two IP addresses on your screen. The one that is on the top bar is the IP of your machine on TryHackMe's network. The IP shown in the *Active Machine Information* panel is the IP of this rooms machine.

With this in mind, to complete the task, copy and paste the IP address of the room's machine to the URL bar of your browser in the VM. If the page isn't loading you may have to restart the rooms machine.

Submit the flag to the input field and move on to the next task. This one does not require a submission so you can just hit the button. 

If you would like to see what careers exist in cyber security you can move onto the <a href="https://tryhackme.com/room/startingoutincybersec">Starting Out In Cyber Sec</a> room. I would highly reccommend taking the time to work through the <a href="https://tryhackme.com/room/introtoresearch">Introduction to Researching</a> room if you are new to this.

-----

Hope this was helpful :)