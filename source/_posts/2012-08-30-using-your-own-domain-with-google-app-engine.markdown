---
layout: post
title: "Using your own domain with Google App Engine"
date: 2012-08-30 11:52
comments: true
categories: CompSci
---
I've just lost too many hours trying to get Infinite Loop to work from my own domain: http://infiniteloop.zakvdm.org

The secret is to follow the instructions on this page: https://developers.google.com/appengine/docs/domain

**BUT!** When you get to the section on CNAME records, the instructions will tell you to create a CNAME record that points to "ghs.googlehosted.com". This is a lie! If you point to "ghs.google.com" instead, then things magically work.
