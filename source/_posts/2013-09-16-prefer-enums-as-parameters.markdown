---
layout: post
title: "Prefer Enums as Parameters"
date: 2013-09-17 23:04
comments: false
categories: [programming]
---

This post goes along with the previous one about [named parameters](http://kwangbkim.com/blog/2013/09/08/named-parameters-for-readability/).  I was re-reading some old notes from [Effective Java](http://www.amazon.com/Effective-Java-Edition-Joshua-Bloch/dp/0321356683/ref=sr_1_1?ie=UTF8&qid=1379471724&sr=8-1&keywords=effective+java) when I came across a little snippet about why enums are preferable as parameter types over things like booleans or strings.

Take this example:
    public int someFormula(int value, bool isFarenheight) {
      // do some stuff...
    }
  
This method signature isn't egregious, but there are a few issues.  The first is that an assumption is made that a celsius value will be passed in if isFarenheight = false.  It's probably what the API is expecting, but who knows for sure?  I suppose the parameter could be renamed to *isFarenheightOrCelsius*.  But say, for whatever reason, a new degree type needs to be included.  Now the situation becomes more complicated.  The API developer will probably have to create a brand new method with a different name, or do a one-off overload that'll make things even more confusing for the client developer.

In short, when in doubt try to prefer enums as parameter types.  It's more readable for the developer and extensible for future changes.