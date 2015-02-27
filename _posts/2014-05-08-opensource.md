---
layout: post 
category : life
title: Open source software, the ultimate winner?
matheq: no
comments: yes
tags : [open source, rednotebook, ubuntu]

---

While I tried to give a sensible answer to the question "What are the pros and cons of Ubuntu as compared with Windows?" raised by a colleague of mine, I got stuck and felt it is really hard to say which one makes more difference for bioinformaticians.
There are plenty of platform independent programming languages and tools, which could achieve the vast majority of developers' targets so far.
Then, problem comes to be OS irrelevant in the term of research.

Open source software empowers users to customize or improve the software, which is the privilege Ubuntu provides.
Here I am going to use [rednotebook](http://rednotebook.sourceforge.net/ "rednotebook") as an example, which is a wonderful open source journal software. 
Since the theme of unity is [MediterraneanDearkest](http://gnome-look.org/content/show.php/MediterraneanNight+Series?content=156782 "MediterraneanDearkest"), while I installed the rednotebook I found the color of tag cloud isn't compatible with unity theme.

![original version](https://2s66lw.blu.livefilestore.com/y2pEwlR0U8C3-uvdlnSWX8-vxz15xaUPmu9f4b1AKWKJBp9w-4w8-mdENF89UnZmPALqZ2CDHzLAsiXibyppqC9kfJ2eZ79Y2n-566T5Z4IC10/rednotebook1.png"original version")

The white background of preview and cloud tag panel of original version is so dazzling, which is just unacceptable.
How to customize it? Here we go.

- Change the css of preview panel

The css file of preview panel is located in the markup interpreting module, which in the folder `rednotebook/util/`.
If rednotebook is installed by root user, then edit the file as below.

{% highlight bash %}
sudo vim /usr/share/rednotebook/rednotebook/util/markup.py
{% endhighlight %}

Add `color` and `background` option in the body function of css module.

{% highlight css  %}
body {
     font-family: %(font)s;
     color:#dddddd;
     background:#2a2a2a;
}
{% endhighlight %}

 
- Change the css of tag cloud panel

Again, add `color` and `background` option in body function of css module in the file `rednotebook/gui/clouds.py` with the same method as above.
Then we will have a customized GUI of rednotebook.

![customized version](https://2s66lw.bl3301.livefilestore.com/y2paJGyC_Dbtaa0gTP63Hv7a715sSJn5fwkfJIKWxsPG0Z4wNHj8iGW37Gd92Mi-erO-th1g0MUB-rEbh9_8DYV6nB15enfFDMxBVpKoXzUbu8/rednotebook2.png "customized version") 

This is the most important pro of Ubuntu compared with Windows, I guess.
