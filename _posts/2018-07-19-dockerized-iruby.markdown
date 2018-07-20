---
layout: post
title:  "Dockerized iRuby"
date:   2018-07-19 20:00:00 -0400
categories: ruby docker jupyter
---

Over the past few months I've been teaching myself Rails in advance of starting a new job
at a Rails shop. I was inexperienced not only in Rails but in Ruby, and wanted to make sure
that I developed good Ruby fundamentals while learning about the Rails framework.

A good REPL is key to mastering a new language, and I wanted a good Ruby REPL by my side
as I was learning. Ruby's command-line REPL wasn't great,
but I was happy to learn that [Jupyter](http://jupyter.org/), the awesomest of REPLs, can be equipped with
a [Ruby kernel](https://github.com/SciRuby/iruby). Perfect!

For maximum convenience and portability, I wanted to Dockerize a Jupyer-based Ruby REPL so
it would be easy to install and spin up on any machine without having to worry at all about
setting up a local environment, installing dependencies, etc.

You can find this Dockerized Ruby REPL on [Github](https://github.com/igorferst/iruby-dockerized/).
Just run `docker-compose up` and you've got the world's loveliest Ruby REPL at your fingertips.
