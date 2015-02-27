---
layout: post
title: 3D Loveletter
matheq: yes
comments: yes
share: yes
category :  technology
tags : [math, r]
---


#### the love story of heartline

>$$r = a(1-\\sin \\theta)$$
>It is said that this is the content of the Descartes sent a love letter to princess..

300 years later, I would like to reappear the romantics of great man. 
And here is the gift to my girlfriend.

####3d loveletter
<img src="http://i.imgur.com/CkNRhNC.gif" width="500" height="500">


####code

{% highlight r %}
require(rgl)
beta<-matrix(seq(0, 2*pi, len=50),50,50)
r<-16*sin(t(beta/2))^3
x<-r*sin(beta)
y<-r*cos(beta)*abs(cos(beta))*0.5
z<-13*cos(t(beta/2))-5*cos(2*t(beta/2))-2*cos(3*t(beta/2))-cos(4*t(beta/2)) 
open3d()
persp3d(x, y, z, ylim=c(max(y)*2,min(y)*2),col="red",alpha=0.8)
persp3d(x-5, y-5, z-1, ylim=c(max(y)*2,min(y)*2),col="hotpink",alpha=0.9,add=TRUE)
text3d(0, y =10, z = -5, texts="I love you",col="red")
text3d(0, y =-10, z = -5, texts="I love you",col="hotpink")
movie3d( spin3d(), duration=5 )
{% endhighlight %}


####reference

- [wiki Descartes](http://zh.wikipedia.org/wiki/%E7%AC%9B%E5%8D%A1%E5%B0%94)
- [Draw the valentine` gift through R](http://cos.name/2012/02/valentines-gift-by-using-r/)

