# Lab session 2017-10-04

## Introduction to the system (MCS, DAMTP)


The DAMTP system is described in https://www.maths.cam.ac.uk/computing/newusers/minibooklet.pdf

MCS (Managed Clustered Service) is the centrally-managed compute
cluster.  Apologies if I still refer to it as PWF (Public Workstation
Facility).


## How to access your email

https://webmail.hermes.cam.ac.uk/

2018: Email alert -- have you switched to Outlook?

## What is subliminal.damtp.cam.ac.uk?

64 core machine in DAMTP.  Lots of CPUs and lots of RAM.  Teaching machine.

## How to login to subliminal

Get your password https://cat.maths.cam.ac.uk/mathspassword/ - via
raven

From a terminal, type:

    ssh -Y sje30@subliminal.maths.cam.ac.uk # change to your CRSID
	xeyes
	
(-Y means that you can run X11, i.e. graphical windows, over the connection.)


## Setting up COMPBIO area on subliminal

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

On subliminal you can make:

    mkdir /local/data/public/CRSID
	
Check
[permissions](https://en.wikipedia.org/wiki/File_system_permissions)
if you have anything private (e.g. coursework).

This disk (`/local/data/public`) is about 15TB, and not backed-up.  Your
files will be deleted in September 2019, so please remove them before
then.

Check out the file `/local/data/SPACEHOGS` to check your disk usage.
As the disk fills up (`df -h /local/data/`) users near the top of the
SPACEHOGS list will be asked to remove their files.


Note also that you will have about 3Gb file space (backed up) on MCS.

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

## Long running jobs

For example, let's all run "slowjob" and then check the machine status
using "top".


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

Consider doing the half-day course offered by the Central UIS: *Unix:
Introduction to the Command Line Interface* https://training.cam.ac.uk/ucs/event/2683594
