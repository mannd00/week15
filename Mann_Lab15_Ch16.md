# Chapter 16: Compiling C Source Code

## How to get git from source

Some systems do not have git preinstalled. I had one that did not want to install from apt easily. One solution is to pull a zip from the official Git github and compile it yourself. Many projects include a makefile which uses the make utility in Linux. Make helps when there are many .c files that all need to be compiled for the project. We will be using it to get git!

First step is to download an archive of the source code. Since we are assuming we do not have git, we can use wget to download the tar.gz

``` wget https://github.com/git/git/archive/v2.17.0.tar.gz ```

Then extract it, and move into it's dir

```
tar -zxf v2.17.0.tar.gz
cd git-2.17.0
```

Then you can do make configure, here you can set additional options. I just used the defaults.

```
make configure
./configure
make all doc info
```

Finally install it!

``` sudo make install install-doc install-html install-info ```

You should now have git installed, and be able to git from anywhere as your user.

## Issues

A relatively minor issue I ran into was not having some of the dependencies installed. In the INSTALL file it outlines what is needed before it can be compiled. I did not read all the way through at first. Like grandpa used to say, if all else fails, try following the directions!

```
sudo apt-get install dh-autoreconf libcurl4-gnutls-dev libexpat1-dev gettext libz-dev libssl-dev
```

