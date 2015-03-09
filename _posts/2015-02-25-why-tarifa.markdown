---
layout: post
title:  "Why tarifa, why wrapping Apache Cordova into another CLI?"
date:   2015-02-24 16:56:49
author: Paul Panserrieu
gravatar: 65920e23fe9e867755920783db9fe3aa
author_twitter: 42loops
categories: introduction
---

[Apache Cordova](http://cordova.apache.org/) is doing a great job allowing web developers to publish mobile apps on stores, however working on various projects I realized I needed to bundle Cordova with extra features to achieve the following goals.

## Work smoothly with a remote team

Did you ever had to explain to someone how to change the signing identity of your Xcode project on a Google Hangout?
Yep, graphical user interfaces are difficult to describe. To get rid of unwanted Hangouts, **your
workflow needs to be expressed as a command line interface**.
Copy pasting strings is much more efficient than trying to explain someone where to click.

The Cordova CLI has almost all the features we need to cover our whole development and publication workflow: only tiny parts are missing. In particular we need to be able to define
multiple app names, to overwrite the `AndroidManifest.xml`'s' `versionCode`, to publish to testers (on [HockeyApp](http://hockeyapp.net/)) and a better interface to the `www` front-end project.

## Lower the barrier to entry without hiding complexity

It is crucial that we can get people up to speed with minimum difficulty: not every web
developer already has experience with Cordova but every developer should be able to easily build apps and publish them to testers.

## Share improvements among all projects

When working on multiple projects with multiple teams it is just easier to reuse
the same tool and have projects working the same way to avoid confusions.
We don't wan't to reinvent the wheel on every project.
For example, cordova hooks will make you spend time on specializing a single project and that will cost you additional time and effort to extract and share the improvements in other projects.

## Keep track of Cordova updates

Cordova grows fast and continuously as mobile SDKs move forward.
It's hard to keep track of all the updates when one is fully focused on coding an application.
Wrapping Cordova help us keep track of changes and improvements but also to test Cordova releases before
using them.

## Automate boring tasks that require attention

Cordova development requires one to perform a lot of boring tasks that require full attention.
It's as if you had to copy a book of 200 pages, the process is simple, you know how to do it,
it's just that you need to stay focused to finish the task at hand without making any errors.

## Interface to any front-end build system

Cordova is agnostic to any JavaScript Framework and for a good reason: nowadays
frameworks and build systems quickly become deprecated. With Cordova you must build your front-end project yourself before building the app.
The wrapper should provide a minimal interface to any front-end build system so that there's a unique command for building apps.

## Produce multiple unique apps on the same platform with a single Cordova project

Every Cordova app has an id and a name. To update the id or the name you must edit multiples files
in the native projet folders. We should be able to define several id and name tuples so that we can build multiple unique apps for the same platform.

## Local downstream distribution of Cordova

<span class='tarifa'>tarifa</span> tries to cover these goals and I hope it will help you build and maintain more Cordova apps. You can see <span class='tarifa'>tarifa</span> as a local downstream distribution of Cordova that helps us improve our workflow.
