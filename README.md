# Lab session 2022-10-06

## Introduction to the system (DAMTP)


The DAMTP system is described briefly in https://www.maths.cam.ac.uk/computing/newusers

There are about 500 linux machines in the DAMTP network.  You can
login to the ones in the 'public' group and to any research group that
you belong.

## How to access your email

https://office.com  New accounts should be on outlook.

## What is subliminal.damtp.cam.ac.uk?

64 core machine in DAMTP, with lots of RAM and disk space.  Teaching
machine.  For the MPhil, this is the main (but not only) DAMTP machine
I recommend you use.

Note that your home directory is shared across all DAMTP machines.
Likewise, your password is the same across all DAMTP machines -- so if
you change your password on one machine, it is effective for all
machines.


## How to login to subliminal

From a terminal, type:

    ssh sje30@subliminal.maths.cam.ac.uk # change to your CRSID
	uname -a 
	
If you have X windows you can instead do:

    ssh -Y sje30@subliminal.maths.cam.ac.uk # change to your CRSID
	xeyes

but installing X (on windows) is currently a pain.

## hotdesk

A simpler way to get a remote graphical connection to subliminal is to
use https://hotdesk.maths.cam.ac.uk

This allows you to run a persistent session on subliminal.  You can
close the browser tab and then come back to the same windows.

screen/tmux are similar programs for text-only terminals.  These allow
you to leave long jobs running and then reconnect later.

## Setting up COMPBIO area on subliminal  (SKIP)

This allows you to run other COMPBIO software by extending your $PATH variable:


One time only you will need to run the following program to configure
your logins:

    /alt/applic/user-maint/sje30/COMPBIO/compbio_runmeonce.sh

Hint: hit TAB to complete filenames.

Logout and then log back in to subliminal for changes to take effect.

Check that you can now run R and other tools:

    R
    4*2

Ctrl-D to exit R.  Then try rstudio:

    rstudio
	

## Rstudio over the network

From a browser visit  http://subliminal.maths.cam.ac.uk:8787/

As long as you have a browser, you can calculate...!

## Managing your files

    quota

Bad news: not much quota, about 4 Gb, by default (although can ask for more).

Good news: home directory is backed up, about every 12 hours.

https://www.maths.cam.ac.uk/computing/storage/backups/mathsbackups

For working with large files. on subliminal you can store them in a
'data' directory (this is not backed up).

    mkdir /local/data/mphilcompbio/2022/CRSID

Check
[permissions](https://en.wikipedia.org/wiki/File_system_permissions)
if you have anything private (e.g. coursework).

This disk (`/local/data/public`) is about 15TB, and NOT backed-up.
Your files will be deleted in September 2023, so
please remove them before then.

Please check the local disk usage by examining 

    du -sh <directory>
	df -h /local/data ## check storage as a whole.


There are also 'store' and 'scratch' data spaces that you might have
access to:

https://www.maths.cam.ac.uk/computing/storage/storage

## exploring quota in detail

    man quota
	quota -h   ### -h is a 'switch' commonly used to show help
	quota -s

# Useful commands to explore

```
ls
cat
less
which 
nano / vi / emacs
cp
mv
mkdir
rm
pwd
cd
passwd


history

screen / tmux

Remote connections:

scp / ssh / rsync / unison

Managing processes:
who
uptime
top
htop
ps ux / kill
nice
```

## Long running jobs

For example, let's all run "slowjob" and then check the machine status
using "top".

/alt/applic/user-maint/sje30/COMPBIO/bin/slowjob is the full path
(remember to use TAB completion).  Check what the file is.

# Laptop issues

## Eduroam

https://help.uis.cam.ac.uk/service/wi-fi


## VPN

https://help.uis.cam.ac.uk/service/network-services/remote-access/uis-vpn

## Remote logins
    ssh ssh.maths.cam.ac.uk
    ssh linux.pwf.cam.ac.uk  (??)

## Accessing files remotely

https://www.maths.cam.ac.uk/computing/remoteaccess/general


Should you keep your files on your laptop, or DAMTP?

DAMTP: files are backed up, but you don't get much quota.  You might
wish to use some service (github, unison) to keep certain directories
in sync.

https://www.maths.cam.ac.uk/computing/remoteaccess/copyingfiles shows
how to use tools like sftp


### moving files in/out of the faculty

zendto is a service for securely sending/receiving large files, up to
20gb.

https://zendto.maths.cam.ac.uk/

### nextcloud

https://www.maths.cam.ac.uk/computing/storage/nextcloud useful as a
dropbox like solution.  But limited quota, e.g. 1-2Gb.


## Working with your laptop

If you have a mac laptop, then all you need is your 'Terminal' app and
X11 and you should be ready.

If you have a windows machine, I recommend you install WSL2 and
perhaps the X server (the latter is a bit fiddly).  You can then start
'Windows Terminal'.  Windows 11 should help a lot here, in that you
won't need X11.


If you have a linux laptop, congratulations, no further edits needed.


## mathematical software

Site licences for software like matlab, mathematica are available so
that you can install these programs on your machine.

https://www.maths.cam.ac.uk/computing/software/maths

## Running long jobs elsewhere

https://www.maths.cam.ac.uk/computing/queuing-system-desktops	describes
a queuing system available for long jobs in maths.  (We will use slurm later.)

# Next steps

Consider doing the half-day course offered by the Central UIS: *Unix:
Introduction to the Command Line Interface* (not running during covid).

more recently, replaced by 'LiL: Unix essential training (online)'
provided by LinkedIn.  https://training.cam.ac.uk/ucs/event/3756056

I would also recommend Software Carpentry guides, e.g.

https://swcarpentry.github.io/shell-novice/

and perhaps, later:

https://swcarpentry.github.io/git-novice/
