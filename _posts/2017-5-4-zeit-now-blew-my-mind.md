---
layout: post
title: zeit now just blew my mind!
---

I had heard the rumblings of this awesome new deployment tool [zeit](https://zeit.co/), but had not tried it out. Then, I heard [Guillermo Rauch](https://twitter.com/rauchg) talking about it on [hanselminutes](https://www.hanselminutes.com/576/deployment-made-easy-with-zeit).

I was taking a break from work, so I decided to see what the big deal is about and then when I tried it:

{: .center}
![_config.yml]({{ site.baseurl }}/images/mind-blown.gif)

Installation is pretty smooth, especially if you have node installed:

```
npm install now -g
```

In the hanselminutes episode Guillermo and Scott talk about proven industry practices that can be used readily as conventions without going through with the [(NIH)](https://en.wikipedia.org/wiki/Not_invented_here) syndrome.

Guillermo and team nailed that in the experience as well, no more going through the signup process.

I ran the executable to try it for the first time, it asked for my email address, sent an activation email with a security code to it almost immediately.

```
now
> Enter your email: johndoe@email.com
> Please follow the link sent to johndoe@email.com to log in.
> Verify that the provided security code in the email matches Reasonable Elephant.
```

I received the email:

```
Hi!

Login attempt from Phoenix, United States

Verify that the provided security code matches Reasonable Elephant before proceeding.

Then please follow this link to verify your email address.
```

Clicking the link automatically activated the now instance.

```
✔ Confirmed email address!
```

After browsing quickly through their website, I created a directory with just an index.html file containing just a h1 **Hello World!**

```
<html>
    <head>
    </head>
    <body>
        <h1>Hello World!</h1>
    </body>
</html>
```

I ran now and bam!, my static html was instantly available:

```
now
> Deploying ~/code/zeit/hello-world under johndoe@email.com
> Using Node.js 7.7.3 (default)
> Ready! https://hello-world-dpmiucvygh.now.sh (copied to clipboard) [3s]
> You (johndoe@email.com) are on the OSS plan. Your code will be made public.
> Initializing…

> Building
> ▲ npm install
> ⧗ Installing:
>  ‣ serve@5.0.4
> ✓ Installed 178 modules [7s]
> ▲ npm start
> > hello-world@ start /home/nowuser/src
> > NODE_ENV='production' serve ./content
> Deployment complete!
```

It even copies the url to the clipboard automatically!

Opened up the browser and there it was, in all its static html glory, accessible to the whole world and that too with a verified certificate.

{: .center}
![_config.yml]({{ site.baseurl }}/images/zeit-hello-world-in-the-cloud.png)

zeit defaults you to the oss plan, the comparison and pricing page is [here](https://zeit.co/pricing).

To see which deployments are running:

```
now ls
> 1 deployment found under johndoe@email.com [770ms]

hello-world (1 of 1 total)
 url                                   inst #    state                 age
 hello-world-dpmiucvygh.now.sh              1    READY                  8m
```

To remove a deployment:

```
now rm hello-world
> The following deployment will be removed permanently:
iDnPpLPq9CNDFJmobMtHB3iU      https://hello-world-dpmiucvygh.now.sh      9m ago
> Are you sure? [y/N] y
> Success! [287ms]
Deployment iDnPpLPq9CNDFJmobMtHB3iU removed
```

Every time you run now without any arguments it will create a brand new instance for you. 

When I saw what the python cloud deployment framework [zappa](https://www.zappa.io/) could do, I was amazed and liked that a lot. 

This, this is something else. 
