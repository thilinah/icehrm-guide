---
description: Here you will learn how to setup your development environment for icehrm
---

# Setup Development Environment

## Clone the IceHrm repo

We recommend using the master branch

```
$ git clone https://github.com/gamonoid/icehrm.git
```

## Check prerequisites

{% hint style="info" %}
You will be more productive when using vagrant for your development environment
{% endhint %}

### Install Virtual Box

Please download and install virtual box for your platform from here: [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)

### Install Vagrant

Instructions for installing vagrant [https://www.vagrantup.com/docs/installation](https://www.vagrantup.com/docs/installation)

Then we need to install vagrant host updater plugin

```text
$ vagrant plugin install vagrant-hostsupdater
```

## Build Frontend Assets

Icehrm has two pakage.json files. Once under the root and the other one under /web directory. NPM should run on both locations

```text
$ npm install
$ cd web
$ npm install
$ cd ..
$ npm install -g gulp-cli
$ gulp
```

## Start Vagrant

The pre-built IceHrm vagrant box contains php 7.3 / nginx and MySQL 5.7 installed. Nginx configurations are loaded from `icehrm/deployment/vagrant`

```text
$ vagrant up
```

Then navigate to [http://icehrm.os](http://icehrm.os) and login with credentails, admin / admin 

