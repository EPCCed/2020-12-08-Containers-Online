---
title: Setup
---
### Website accounts to create
Please seek help at the start of the lesson if you have not been able to establish a website account on:
- The [Docker Hub](http://hub.docker.com). We will use the Docker Hub to download pre-built container images, and for you to upload and download container images that you create, as explained in the relevant lesson episodes.

### Files to download

Download the [`docker-intro.zip`](/files/docker-intro.zip). _This file can alternatively be downloaded from the `files` directory in the [course GitHub repository](https://github.com/EPCCed/2020-12-08-Containers-Online)._

Move the downloaded file to your Desktop and unzip it. It should unzip to a folder called `docker-intro`. 

### Software to install: Docker

Docker can be installed on Windows 10, macOS and Linux. However, in some cases, installing Docker on your laptop may, unfortunately, not be completely straightforward if you do not have significant technical experience. We have helpers on hand that have worked their way through the install process but be prepared for some troubleshooting.

Please try to install the appropriate software from the list below depending on the operating system that your laptop is running:

#### **Microsoft Windows:**
**You must have admin rights to run docker!** Some parts of the lesson will work without running as admin but if you are unable to `Run as administrator` on your machine some elements of this workshop might not work as described.

On Windows 10, you will need to install [Docker Desktop for Windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows). 

_Previously Windows 10 Home users needed to install an alternative version of Docker - [Docker Toolbox](https://docs.docker.com/docker-for-windows/docker-toolbox/) - however, this is now deprecated. Docker Desktop for Windows can now also be installed on Windows 10 Home Edition_

**If you have Windows 10 Pro Edition (or Windows 10 Enterprise or Education):** 

 - See [these instructions](https://docs.docker.com/docker-for-windows/install/) for installing Docker Desktop for Windows.

**If you have Windows 10 Home Edition:**

 - See [these instructions](https://docs.docker.com/docker-for-windows/install-windows-home/) for installing Docker Desktop for Windows on Windows 10 Home.

_Note that the above installation instructions highlight a minimum version or "build" that is required to be able to install Docker on your Windows 10 system. See [Which version of Windows operating system am I running?](https://support.microsoft.com/en-us/windows/which-version-of-windows-operating-system-am-i-running-628bec99-476a-2c13-5296-9dd081cdd808) for details of how to find out which version/build of Windows 10 you have._

If you are unable to follow the above instructions to install Docker on your Windows system, the final release of the deprecated Docker Toolbox version of Docker for Windows can be downloaded from the [releases page of the Docker Toolbox GitHub repository](https://github.com/docker/toolbox/releases). (Download the `.exe` file for the Windows installer). _Please note that this final release of Docker Toolbox includes an old version of Docker and you are strongly advised not to attempt to use this for any production use. It will, however, enable you to follow along with, and participate in, this course._

#### **Apple macOS:**

Install [Docker Desktop for Mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac). _macOS version 10.14 or newer is required to install this version._

If you have an older version of macOS, you could try installing the [now deprecated Docker Toolbox](https://docs.docker.com/docker-for-windows/docker-toolbox/), for the purpose of participating in this course, from the [releases page of the Docker Toolbox GitHub repository](https://github.com/docker/toolbox/releases). (Download the `.pkg` file for the macOS installer).

_Please note that this final release of Docker Toolbox includes an old version of Docker and you are strongly advised not to attempt to use this for any production use. It will, however, enable you to follow along with, and participate in, this course._

#### **Linux:**
There are too many varieties of Linux to give precise instructions here, but hopefully you can locate documentation for getting Docker installed on your Linux distribution. It may already be installed. If it is not already installed on your system, the [Install Docker Engine](https://docs.docker.com/engine/install/) page provides an overview of supported Linux distributions and pointers to relevant installation information. Alternatively, see:

 - [Docker Engine on CentOS](https://docs.docker.com/install/linux/docker-ce/centos/)
 - [Docker Engine on Debian](https://docs.docker.com/install/linux/docker-ce/debian/)
 - [Docker Engine on Fedora](https://docs.docker.com/install/linux/docker-ce/fedora/)
 - [Docker Engine on Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

_Note that on Linux, you will either need to run Docker commands as root using `sudo` or [create a docker group to run without sudo](https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user)_


### A quick tutorial on copy/pasting file contents from episodes of the lesson
Let's say you want to copy text off the lesson website and paste it into a file named `myfile` in the current working directory of a shell window. This can be achieved in many ways, depending on your laptop's operating system, but routes I have found work for me:

 - macOS and Linux: you are likely to have the `nano` editor installed, which provides you with a very straightforward way to create such a file, just run `nano myfile`, then paste text into the shell window, and press <kbd>control</kbd>+<kbd>x</kbd> to exit: you will be prompted whether you want to save changes to the file, and you can type <kbd>y</kbd> to say "yes".

 - Microsoft Windows running `cmd.exe` shells:
   - `del myfile` to remove `myfile` if it already exists;
   - `copy con myfile` to mean what's typed in your shell window is copied into `myfile`;
   - paste the text you want within `myfile` into the shell window;
   - type <kbd>control</kbd>+<kbd>z</kbd> and then press <kbd>enter</kbd> to finish copying content into `myfile` and return to your shell;
   - you can run the command `type myfile` to check the content of that file, as a double-check.

 - Microsoft Windows running PowerShell:
   - The `cmd.exe` method probably works, but another is to paste your file contents into a so-called "here-string" between `@'` and `'@` as in this example that follows (the ">" is the prompt indicator):

        ``` 
        > @'
        Some hypothetical
        file content that is

        split over many

        lines.
        '@ | Set-Content myfile -encoding ascii
         ```

## 3. SSH client

All attendees should have an SSH client installed.
SSH is a tool that allows us to connect to and use a remote computer, within a terminal window, as our own.
Please follow the directions below to install an SSH client for your system.

**Windows**

Modern versions of Windows have SSH available in Powershell. You can test if it is available by typing `ssh --help` in Powershell. If it is
installed, you should see some useful output. If it is not installed, you will get an error. If SSH is not available in Powershell, then
you should install MobaXterm as described below.

An alternative is to install MobaXterm from [http://mobaxterm.mobatek.net](http://mobaxterm.mobatek.net). You will want to get the Home edition (Installer edition). However, if Git Bash works, you do not need this.

**macOS**

macOS comes with SSH pre-installed, so you should not need to install anything.

**Linux**

Linux users do not need to install anything, you should be set!

## 4. Account on ARCHER2

Please sign up for your account on our HPC machine, [ARCHER2](https://www.archer2.ac.uk/), which will be available to
you for the duration of the course and for a few days afterwards, to allow you to
complete the practical exercises and put some of what you have learned into practice.

### 4.1 Sign up for a SAFE account

To sign up, you must first register for an account on [SAFE](https://safe.epcc.ed.ac.uk/) (our service administration web application):

If you are already registered on the ARCHER or Tier-2 SAFE you do not need to re-register. Please proceed to the next step.

1. Go to the [SAFE New User Signup Form](https://safe.epcc.ed.ac.uk/signup.jsp)
2. Fill in your personal details. You can come back later and change them if you wish. _**Note:** you should register using your institutional or company email address - email domains such as gmail.com, outlook.com, etc. are not allowed to be used for access to ARCHER2_
3. Click “Submit”
4. You are now registered. A single use login link will be emailed to the email address you provided. You can use this link to login and set your password.

### 4.3 Sign up for an account on ARCHER2 through SAFE

In addition to your password, you will need an SSH key pair to access ARCHER2. There is useful guidance on how
to generate SSH key pairs in [the ARCHER2 documentation](https://docs.archer2.ac.uk/user-guide/connecting/#ssh-key-pairs).
It is useful to have your SSH key pair generated before you request an account on ARCHER2 as you can add it when 
you request the account

1. [Login to SAFE](https://safe.epcc.ed.ac.uk)
2. Go to the Menu "Login accounts" and select "Request login account"
3. Choose the `ta007` project “Choose Project for Machine Account” box and click "Next"
4.  Select the *ARCHER2* machine in the list of available machines
5.  Click *Next*
6.  Enter a username for the account and an SSH public
    key
    1.  If you do not specify an SSH key at this stage, your default
        key will be used (if you have one). For users who had an ARCHER
        account, the default key will be your ARCHER SSH key.
    2.  You can always add an SSH key (or additional SSH keys) using
        the process described below.
7.  Click *Request*

Now you have to wait for the course organiser to accept your request to register. When this has happened, your account will be created on ARCHER2.
Once this has been done, you should be sent an email. _If you have not received an email but believe that your account should have been activated, check your account status in SAFE which will also show when the account has been activated._ You can then pick up your one shot initial password for ARCHER2 from your SAFE account.

### 4.4 Log into ARCHER2

You should now be able to log into ARCHER2 by following the [login instructions in the ARCHER2 documentation](https://docs.archer2.ac.uk/user-guide/connecting/#ssh-clients).

## (Optional) Install Singularity on your local system

The Singularity part of this course will be undertaken on ARCHER2. If you do not wish to use ARCHER2 to run your Singularity images, you will need to install Singularity on your local system. _These instructions are optional and are not required to complete the course._

If you are running Linux and would like to install Singularity locally on your system, Singularity provide the free, open source [Singularity Community Edition](https://sylabs.io/singularity/). 

You will need to install various dependencies on your system and then build Singularity from source code. If you have Linux systems knowledge and would like to attempt a local install of Singularity, you can find full details of the installation process in the [INSTALL.md](https://github.com/sylabs/singularity/blob/master/INSTALL.md) file within the Singularity repository. This file explains how to install the prerequisites and build and install the software. Singularity is written in the [Go](https://golang.org/) programming language and Go is the main dependency that you'll need to install on your system. The process of installing Go and any other requirements is detailed in the INSTALL.md file.

If you do not have access to a Linux system where you can build and install Singularity but you have administrative privileges on another system, you could look at installing a virtualisation tool such as [VirtualBox](https://www.virtualbox.org/) on which you could run a Linux Virtual Machine (VM) image. Within the Linux VM image, you will be able to install Singularity. Again this is beyond the scope of the course.

If you have a Mac system, you can also try the beta release of [Singularity Desktop for macOS](https://sylabs.io/singularity-desktop-macos/). (This tool is progressing all the time though it did not work well for the instructors at the time when this material was initially written!)


{% include links.md %}

{% comment %}
<!--  LocalWords:  myfile kbd links.md md endcomment
-->
{% endcomment %}

