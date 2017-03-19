# Learning/Golang

I started learning Go and I am summing up all the important information I should not forget and that I found important when I started with the language.

## Summary

- [Introduction](#introduction)
  - [About my setup](#about-my-setup)
  - [Installation](#installation)
  - [Setting up the PATH](#setting-up-the-path)
  - [Setting up the workspace](#setting-up-the-workspace)
  - [Setting up vim](#setting-up-vim)
- [Projects](#projects)
  - [Hello world](#hello-world)

## Introduction

These are basic information that will make it easier to start with Go.

### About my setup

As the time I write this, I am using **Ubuntu 16.10**. Somethings I do now may be different from newer or older versions of Ubuntu as well as from other Linux distros or other operating systems.

### Installation

I decided to download the newest stable version of Go (at the time being it is version `1.8`) from [the official website](https://golang.org/dl/).
It is possible to install from the Ubuntu repositories likewise, but the version in Ubuntu repos, at the time I write this, is `1.6`.
To install from the `tar.gz`, just run:

    $ curl -o - https://storage.googleapis.com/golang/go1.8.linux-amd64.tar.gz | sudo tar xzvf - -C /usr/local/

The command will download and extract `go1.8.linux-amd64.tar.gz` to `/usr/local/`. The resulting directory will be something like this:

    $ tree -L 1 /usr/local/go/
    /usr/local/go/
    ├── api
    ├── AUTHORS
    ├── bin
    ├── blog
    ├── CONTRIBUTING.md
    ├── CONTRIBUTORS
    ├── doc
    ├── favicon.ico
    ├── lib
    ├── LICENSE
    ├── misc
    ├── PATENTS
    ├── pkg
    ├── README.md
    ├── robots.txt
    ├── src
    ├── test
    └── VERSION

    9 directories, 9 files

You now have Go correctly installed! But before you start using it, you will need to [setup your PATH](#setting-up-the-path) and your [Go workspace](#setting-up-the-workspace) (really important!).

### Setting up the PATH

### Setting up the workspace

### Setting up vim

## Projects

### Hello world

