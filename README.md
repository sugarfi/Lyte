# Lyte
Lyte is a command line tool to handle dependency resolution and package installation.
It stores a package manager command for each target, for example pip3 for Python 3
or npm for Node.js. Then it just runs that command on each package the user has
given. It reads packages from a Lytefile, similar to GNU Make or Docker. To use it,
simply download the file and install it to somewhere in your PATH, then run:
```
you@computer$ lyte setup
```
This will create a .lyte/ directory in your home folder and set it up. Then in a project,
create a Lytefile. For each thing you need to install, add a line to the file in the
format:
```
<target>: <package 1> <package 2> ... <package n>
```
The available targets are python3, python2, debian, arch, and node. Once you have a
Lytefile, simply run:
```
you@computer$ lyte install
```
This will install your packages.
  
## Installing
To install Lyte, simply clone this repo and then run:
```
you@computer$ sudo install lyte /usr/bin
```

## Options
-f, --file:
    Use a custom file instead of Lytefile.
-d, --defaults:
    Use a custom target file instead of the default, ~/.lyte/defaults.conf.
    The defaults file has the same format as a Lytefile, for example:
        python3: pip3 install
        node: npm install
-o, --output:
    Do not suppress the output of the packager commands.
-e, --error:
    Supresses stderr for packager commands.

## Credits
Lyte was written by Solomon Jackson.
You can use, modify, sell, or do whatever you want with this software however you wish.
It is totally free and open source.
