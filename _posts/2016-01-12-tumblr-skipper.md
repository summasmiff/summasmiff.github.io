---
layout: post
title: Updating permissions for the TumblrSkipper Chrome extension
quote: be cool to your users
image: false
video: false
---

Today I updated the very first Chrome extension I ever made, TumblrSkipper. Inspired by my buddy Carl's [HeraldSkipper](https://github.com/c-ro/HeraldSkipper) extension, I made TumblrSkipper as my version of a "Hello World". It's very simple, but it solved a problem I was having, which is the only way I can stick with a personal project.

Tumblr had introduced an annoying new "feature": instead of a tumblr blog's name acting as a normal link, it pulled up a popover style preview of the blog, preventing my normal tumblr flow of opening a bunch of tabs and coming back to them later.

This was solved very simply by using jQuery to capture the click event that created the popover and going straight to the url instead. You can see that function on my [Github repo](https://github.com/summasmiff/TumblrSkipper).

Because it was so simple, I didn't spend much time on packaging it up as an extension, which was quickly noticed by [Sarah](http://www.3till7.net/), who pointed out that I was requesting access to a user's entire browsing history when they installed my dumb little app.

This was because of some boilerplate I left in the manifest.json:
{% highlight json %}
permissions: [
"tabs",
"webNavigation",
"*://*/*"
]
{% endhighlight %}

The last line, with all the asterisks, was asking for permission to track the user's browsing to know when to invoke the extension - and with all the wildcards, it wanted everything.

Since my extension is really only for the Tumblr dashboard, it was easy enough to restrict permission to where I really needed it:
{% highlight json %}
permissions: [
"tabs",
"webNavigation",
"https://www.tumblr.com/*"
]
{% endhighlight %}

I could've gone further, and restricted it to the dashboard alone, but this will make it a lot less scary for the users. Republishing a Chrome extension is simple - bump the version in the manifest, upload it in the developer dashboard, unpublish, republish.

Get the [TumblrSkipper](https://chrome.google.com/webstore/detail/tumblrskipper/cofjhhfhgfpdglobncjkfdmmpdkmfgdc) on the Chrome store
