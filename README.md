# Lab session 2016-10-03

Basic aims for lab

## Introduction to the system (PWF, DAMTP).


The DAMTP system is described in http://www.maths.cam.ac.uk/computing/learning/unixbook.pdf

PWF is the centrally-managed compute cluster.
## How to access your email

https://webmail.hermes.cam.ac.uk/

## What is subiculum.damtp.cam.ac.uk?

64 core machine in DAMTP.

## How to login to subiculum

From a terminal, type:

    ssh -Y sje30@subliminal.maths.cam.ac.uk # change to your CRSID

(-Y means that you can run X11, i.e. graphical windows, over the connection.)


## Setting up COMPBIO area on subiculum

This allows you to run other COMPBIO software by extending your $PATH variable:


One time only you will need to run the following program to configure
your logins:

    /alt/applic/user-maint/sje30/COMPBIO/compbio_runmeonce.sh

Hint: hit TAB to complete filenames.

Logout and then log back in to subliminal for changes to take effect.

Check that you can now run R and other tools:

    R
    4*2
    require(limma)

Ctrl-D to exit R.  Then try rstudio:

    rstudio
	

## Rstudio over the network

From a browser visit  http://subliminal.maths.cam.ac.uk:8787/

As long as you have a browser, you can calculate...!

## Managing your files

    quota

Bad news: not much quota by default (although can ask for more).

Good news: backed up.


On subiculum you can make:

    mkdir /local/data/public/CRSID
	
Check
[permissions](https://en.wikipedia.org/wiki/File_system_permissions)
if you have anything private (e.g. coursework).

See also "store-space".

# Top commands to explore

See also the DAMTP booklet.

```
ls
cp
mv
mkdir
rm
pwd
cd
passwd

top
htop
uptime
history

screen

scp / ssh / rsync / unison
```


# Laptop issues

## Eduroam

http://www.ucs.cam.ac.uk/wireless/eduroam/localusers


## VPN

http://www.ucs.cam.ac.uk/vpn

## Remote logins

    ssh linux.pwf.cam.ac.uk
    ssh ssh.maths.cam.ac.uk

## Accessing files remotely

https://lapserv.maths.cam.ac.uk/docs/files.html

# Next steps

Consider doing the half-day course offered by the Central UIS.


