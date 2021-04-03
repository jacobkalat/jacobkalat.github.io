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

To connect your VM (virtual machine) to TryHackMe's network we are going to use OpenVPN. To get started open up a terminal and type the following to update your machine. This explanation is for 

<!-- {% highlight %}
foo@bar:~$ sudo apt update && sudo apt upgrade
{% endhighlight %}

Allow this to finish. After, install the OpenVPN package using

{% highlight %}
foo@bar:~$ sudo apt install openvpn
{% endhighlight %}


Now that we have OpenVPN installed, we need to get our configuration file from TryHackMe. Navigate to their page explaining connecting via <a href="https://tryhackme.com/access?o=vpn">OpenVPN</a>. After changing your region to your preference, click the button that says *Download My Configuration File*. 

![placeholder](/img/tryhackme/openvpn-access-details.png "OpenVPN Access Details")

Now that the file is downloaded, we can open a terminal and connect using the following command

{% highlight %}
foo@bar:~$ sudo openvpn /path/to/config_file
{% endhighlight %}

Replace */path/to/config_file* with the location of the downloaded configuration file. If you ran this command correctly, you should see that your IP address is not long 0.0.0.0 in the *OpenVPN Access Details* pane. This is now your local IP address in TryHackMe's network.

### Finishing the Tutorial

Now back at the <a href="https://tryhackme.com/room/tutorial">Tutorial Room</a> you should see two IP addresses on your screen. The one that is on the top bar is the IP of your machine on TryHackMe's network. The IP shown in the *Active Machine Information* panel is the IP of this rooms machine.

With this in mind, to complete the task, copy and paste the IP address of the room's machine to the URL bar of your browser in the VM. If the page isn't loading you may have to restart the rooms machine.  -->


> Curabitur blandit tempus porttitor. Nullam quis risus eget urna mollis ornare vel eu leo. Nullam id dolor id nibh ultricies vehicula ut id elit.

Etiam porta **sem malesuada magna** mollis euismod. Cras mattis consectetur purus sit amet fermentum. Aenean lacinia bibendum nulla sed consectetur.

## Inline HTML elements

HTML defines a long list of available inline tags, a complete list of which can be found on the [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/HTML/Element).

- **To bold text**, use `<strong>`.
- *To italicize text*, use `<em>`.
- Abbreviations, like <abbr title="HyperText Markup Langage">HTML</abbr> should use `<abbr>`, with an optional `title` attribute for the full phrase.
- Citations, like <cite>&mdash; Mark otto</cite>, should use `<cite>`.
- <del>Deleted</del> text should use `<del>` and <ins>inserted</ins> text should use `<ins>`.
- Superscript <sup>text</sup> uses `<sup>` and subscript <sub>text</sub> uses `<sub>`.

Most of these elements are styled by browsers with few modifications on our part.


### Code

Cum sociis natoque penatibus et magnis dis `code element` montes, nascetur ridiculus mus.

{% highlight js %}
// Example can be run directly in your JavaScript console

// Create a function that takes two arguments and returns the sum of those arguments
var adder = new Function("a", "b", "return a + b");

// Call the function
adder(2, 6);
// > 8
{% endhighlight %}

Aenean lacinia bibendum nulla sed consectetur. Etiam porta sem malesuada magna mollis euismod. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa.

### Gists via GitHub Pages

Vestibulum id ligula porta felis euismod semper. Nullam quis risus eget urna mollis ornare vel eu leo. Donec sed odio dui.

{% gist 5555251 gist.md %}

Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum. Nullam quis risus eget urna mollis ornare vel eu leo. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec sed odio dui. Vestibulum id ligula porta felis euismod semper.

### Lists

Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Aenean lacinia bibendum nulla sed consectetur. Etiam porta sem malesuada magna mollis euismod. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.

* Praesent commodo cursus magna, vel scelerisque nisl consectetur et.
* Donec id elit non mi porta gravida at eget metus.
* Nulla vitae elit libero, a pharetra augue.

Donec ullamcorper nulla non metus auctor fringilla. Nulla vitae elit libero, a pharetra augue.

1. Vestibulum id ligula porta felis euismod semper.
2. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.
3. Maecenas sed diam eget risus varius blandit sit amet non magna.

Cras mattis consectetur purus sit amet fermentum. Sed posuere consectetur est at lobortis.

<dl>
  <dt>HyperText Markup Language (HTML)</dt>
  <dd>The language used to describe and define the content of a Web page</dd>

  <dt>Cascading Style Sheets (CSS)</dt>
  <dd>Used to describe the appearance of Web content</dd>

  <dt>JavaScript (JS)</dt>
  <dd>The programming language used to build advanced Web sites and applications</dd>
</dl>

Integer posuere erat a ante venenatis dapibus posuere velit aliquet. Morbi leo risus, porta ac consectetur ac, vestibulum at eros. Nullam quis risus eget urna mollis ornare vel eu leo.

### Images

Quisque consequat sapien eget quam rhoncus, sit amet laoreet diam tempus. Aliquam aliquam metus erat, a pulvinar turpis suscipit at.


![placeholder](http://placehold.it/400x200 "Medium example image")
![placeholder](http://placehold.it/200x200 "Small example image")

### Tables

Aenean lacinia bibendum nulla sed consectetur. Lorem ipsum dolor sit amet, consectetur adipiscing elit.

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Upvotes</th>
      <th>Downvotes</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <td>Totals</td>
      <td>21</td>
      <td>23</td>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>Alice</td>
      <td>10</td>
      <td>11</td>
    </tr>
    <tr>
      <td>Bob</td>
      <td>4</td>
      <td>3</td>
    </tr>
    <tr>
      <td>Charlie</td>
      <td>7</td>
      <td>9</td>
    </tr>
  </tbody>
</table>

Nullam id dolor id nibh ultricies vehicula ut id elit. Sed posuere consectetur est at lobortis. Nullam quis risus eget urna mollis ornare vel eu leo.

-----

Want to see something else added? <a href="https://github.com/poole/poole/issues/new">Open an issue.</a>
