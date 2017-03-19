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

You now have Go correctly installed! But before you start using it, you will need to [setup your PATH](#setting-up-the-path) and your [Go workspace](#setting-up-the-workspace) (really important!).

### Setting up the PATH

In order to be able to run Go, we first need to tell our shell where it can find the Go binaries we installed earlier.

I use [fish](http://fishshell.com/) as my default shell. To configure its PATH, run:

    $ set -U fish_user_paths $fish_user_paths /usr/local/go/bin

To configure the PATH in `bash` (the default shell of the majority of the operating systems), open your `~/.bashrc` with your preferred text editor and add `export PATH=$PATH:/usr/local/go/bin` to it.

Now you need to reload your shell configuration (you can just open a new tab or window in your terminal) and you will be able to run go. To check if everything is fine, run:

    $ go version
    go version go1.8 linux/amd64

If you receive an output similar to the one above, it means the PATH was set up correctly. Now, to start using go, you just need to [setup the workspace](#setting-up-the-workspace).

### Setting up the workspace

Go has a strict directory structure that you must follow. It looks like the following (I explain with more details later on):

    $ tree -L 4 ~/code/go/
    /home/gabriell/code/go/
    ├── bin
    │   └── hello
    ├── pkg
    │   └── linux_amd64
    │       ├── github.com
    │       │   └── kr
    │       └── golang.org
    │           └── x
    └── src
        ├── github.com
        │   ├── gabriellhrn
        │   │   ├── hello
        │   └── kr
        │       └── pty
        └── golang.org
            └── x
                ├── crypto
                └── net

First of all, you need to define a directory where you are going to put all of your Go code. You may create a folder wherever you want, e.g. you may have a folder called `code` where you store your projects. In that case, create a folder called `go` inside of it:

    $ mkdir ~/code/go

Done! Now you will tell Go where your Go code is located. For `fish`, run:

    $ set -gx GOPATH $HOME/code/go

For `bash`, open `~/.bashrc` with your preferred text editor and add `export GOPAHT=$HOME/code/go` to it.

You will need to reload your shell configuration (you can just open a new tab or window in your terminal).

**Now it is important to know how Go workspace works**. The Go workspace separates your project in some kind of namespaces. Look at the workspace structure above for reference.

- `bin`: contains the compiled binaries built from your source code
- `pkg`: contains the packages you `import` to your code. They are downloaded from the Internet
- `src`: the source code used to compile binaries. **You will put *your* source code into** `src/github.com/<your_username>`

If you follow that structure, you are not going to have problems when running `go get`, `go build` or `go run`.

### Setting up vim

I use vim as my editor and I added the plugin [vim-go](https://github.com/fatih/vim-go) to enhance the Go syntax.

## Projects

### Hello world

When you start learning a new language your first program must be a `Hello World` or you will be doomed forever in that language.
This is a simple program. You don't even need to respect Go's workspace, because you are not going to import any packages. You will just use `fmt` from the standard library. To run this program:

    $ cd projects/hello-world
    $ go run hello.go
    Hello world!

And that's it!

