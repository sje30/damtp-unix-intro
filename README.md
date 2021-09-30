# Lab session 2021-10-06

## Introduction to the system (MCS, DAMTP)


The DAMTP system is described in
https://www.maths.cam.ac.uk/computing/newusers/minibooklet.pdf and the
longer guide is at https://www.maths.cam.ac.uk/computing/ComputingBooklet.pdf

https://www.maths.cam.ac.uk/computing/files/newusers/New%20starter%20IT%20essentials%20V1.0.pdf

MCS (Managed Clustered Service) is the centrally-managed compute
cluster.  Apologies if I still refer to it as PWF (Public Workstation
Facility).  These machines are to be found in the CATAM room and
around your colleges.


## How to access your email

https://office.com  New accounts should be on outlook.

## What is subliminal.damtp.cam.ac.uk?

64 core machine in DAMTP.  Lots of CPUs and lots of RAM.  Teaching machine.

## How to login to subliminal

From a terminal, type:

    ssh sje30@subliminal.maths.cam.ac.uk # change to your CRSID
	uname -a 
	
If you have X windows you can instead do:

    ssh -Y sje30@subliminal.maths.cam.ac.uk # change to your CRSID
	xeyes


## hotdesk

A simpler way to get a remote graphical connection to subliminal is to
use https://hotdesk.maths.cam.ac.uk

This allows you to run a persistent session on subliminal.  You can
close the browser tab and then come back to the same windows.


screen/tmux are similar programs

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

    mkdir /local/data/public/2021/CRSID
	
Check
[permissions](https://en.wikipedia.org/wiki/File_system_permissions)
if you have anything private (e.g. coursework).

This disk (`/local/data/public`) is about 15TB, and NOT backed-up.
files in /local/data/public/2021 will be deleted in September 2022, so
please remove them before then.

Please check the local disk usage by examining 
http://monitor.maths.cam.ac.uk/cgi-bin/agedu//subliminal/

Note also that you will have about 3Gb file space (backed up) on MCS.

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

http://www.ucs.cam.ac.uk/wireless/eduroam/localusers


## VPN

http://www.ucs.cam.ac.uk/vpn

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

### nextcloud

https://www.maths.cam.ac.uk/computing/storage/nextcloud useful as a
dropbox like solution.


## Working with your laptop

If you have a mac laptop, then all you need is your 'Terminal' app and
X11 and you should be ready.

If you have a windows machine, I recommend you install WSL2 and
perhaps the X server (the latter is a bit fiddly).
https://github.com/microsoft/wslg promises to do both the linux + X11
graphics together.

If you have a linux laptop, congratulations.

# Next steps

Consider doing the half-day course offered by the Central UIS: *Unix:
Introduction to the Command Line Interface* (not running during covid).

more recently, replaced by 'LiL: Unix essential training (online)'
provided by LinkedIn.  https://training.cam.ac.uk/ucs/event/3756056

I would also recommend Software Carpentry guides, e.g.

https://swcarpentry.github.io/shell-novice/

and perhaps, later:

https://swcarpentry.github.io/git-novice/
