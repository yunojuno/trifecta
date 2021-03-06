# Trifecta

_(A trifecta is a a bet in which the person betting forecasts the first three finishers in a race in the correct order. This project has nothing to do with betting; it's a project in which three loosely related technologies are assembled in a specific order to solve a specific problem. My misuse of the word is understood and intentional. If you're a word-nerd, please forgive me.)_

This project contains the configuration required to build and run a developer's environment using Vagrant, Docker, and Virtualenv together. The sample code is python (django), but the principles would work for other stacks.

The end goal is to build a fresh environment in which a developer can cut code without having to worry about the setup and configuration of external services, such as postgres, redis, memcache. They can concentrate on editing code, and running the application.

The end results looks like this:

```
========================================================
Ubuntu 14.04 ........... localhost .......... Vagrant
|
+- nginx ............... localhost:80/443 ... Docker
   |
   +- application ...... localhost:8000 ..... Virtualenv <- developer works here
      |
      +- postgres ...... localhost:5432 ..... Docker
      |
      +- redis ......... localhost:6379 ..... Docker
      |
      +- memcached ..... localhost:11211 .... Docker
      |
      +- elasticsearch . localhost:9200 ..... Docker
========================================================
```

The background to this project can be found on the YunoJuno tech blog in the following articles:

* [Vagrant, Docker, Virtualenv - the dev trifecta](http://bit.ly/1cvcHwT)
* [Vagrant as the base OS](http://bit.ly/1cvcLwn)
* [Docker services](http://bit.ly/1RLvOm1)
* [Virtualenv](http://bit.ly/1TpBsfu) (not yet published)

The output of this project is available as a Vagrant box on the Atlas repo as [yunojuno/trifecta](http://bit.ly/1H2KifK)

---

**Update** (15-Jan-2016)

This project now includes a [Packer](https://www.packer.io/intro/) template, which is connected to the Atlas directory, so that the [yunojuno/trifecta](http://bit.ly/1H2KifK) Vagrant box is built automatically from the ground up. It took a bit of experimentation to get it working, so feel free to use this as a template for your own templates.
