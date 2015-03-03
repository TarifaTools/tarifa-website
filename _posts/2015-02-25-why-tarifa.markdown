---
layout: post
title:  "Why tarifa, why wrapping Apache Cordova into another CLI?"
date:   2015-02-24 16:56:49
author: Paul Panserrieu
author_twitter: 42loops
categories: introduction
---

Apache Cordova is doing a great job allowing web developer to publish mobile apps on stores.
While working on various projets, I came to the point where I needed to bundle Cordova with
some extra features to statisfy the following goals.

## Work smoothly with a remote team

Did you ever explained anyone how to change the signing identity of your project in XCode on a google hangout?
Yep, graphical user interfaces are difficult to describe. To get rid of unwanted hangout, **all your
workflow needs to be expressed as a command line interface**.
Copy pasting strings is much more efficient than trying to explain someone where to click.

The Cordova CLI has fast all the features required, only tiny parts are missing to cover
all the developpement and publication workflow: like been able to define
multiple app names, to overwrite the `AndroidManifest.xml` `versionCode`, to publish to tester or a better interface to
the `www` front-end project.

## Lower the entry barrier without hiding complexity

It is crusial to be able to bring people on board with less friction as possible: not every web
developer has already some experiences with Cordova but every developer should be able to easily build and publish
to tester.

## Share improvements on all projects

While working on multiple projects with multiple teams, it is just easier to reuse
the same tool and have projects working the same way to avoid confusion.
Let's try to not redo multiple time the same things.
For example, codova hooks will encourage spending times on specializing your project.
And it will recost time and efforts to extract improvements and spread them into all projects.

## Keep track of Cordova changes

Cordova grows fast and continously has mobile SDKs increase their version number.
It's hard to keep track of all improvements when fully concentrated on coding a project.
Wrapping it allows to keep track of changes and improvements but also to test releases before
using them.

## Reduce boring tasks that requires attention

Cordova developpement requires to execute a lot of boring tasks that requires your full attention.
It's like you need to copy a book of 200 pages, the process is simple, you know how to do it,
it's just that you need to keep concentrate to finish such a task without making errors.

## Interface to any front-end build system

Cordova is agnostic to any JavaScript Framework and it's good so. Now a days,
frameworks and build systems evolves very fast and are changed quickly.
It should provide a minimal interface to any frontend build system allowing a unic command for building apps.

## Produce multiple unique apps on the same platform with a single Cordova project

Each cordova app is bounded to an id and a name, modifying one of them results in the change of multiples files
in the native projet folders. It should beeing able to define multiple id and name combinations to build multiples unic apps for
the same platform.

## Local downstream distribution of Cordova

<span class='tarifa'>tarifa</span> tries to cover all these goals and I hope will helps you to build and maintain more Cordova apps.
