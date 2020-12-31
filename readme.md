## Linux Basics

Below is a list of topics and skills a person should have to be minimally comfortable working with linux.
If you understand all of the topics below, you should be able to login and navigate the system.



## Linux distros

    - linux is very modular, you can swap out nearly any part of the system with some alternative
    - The one component you cant swap is the kernel, all linux distros use the linux kernel
    - There are operating systems with different kernels such as Unix, BSD, MacOS and others might use some of the same components as linux, but they arent linux because they dont use the linux kernel.
    - there are thousands of linux distros with different combinations of major components.
    - some of the major componets and features include:
        - init system (systemd, upstart, sysVinit)
        - window manager (none, Gnome, KDE, XFCE, Cinnamon, Mate, and many more)
        - package manager (yum, apt, dnf, pacman, apk, and more)
        - file system (ext3, ext4, zft, btrfs, and more)
        - release model (fixed or rolling)

    see also: https://distrowatch.com

## Create a VM for learning

Below are instructions to create a temp linux VM

### On Mac

    # install homebrew
    brew cask install virtualbox
    brew cask install vagrant

    # create a Vagrant file that defines a centos (systemd, yum) VM
    # see also https://app.vagrantup.com/boxes/search
    mkdir centos8
    cd centos8
    vagrant init centos/8

    # download a centos image and start it
    vagrant up

    # ssh into the running VM (type 'exit' to logout)
    vagrant ssh

    # stop the VM
    vagrant halt


### On Windows

    TODO

## Init Systems

    init systems are responsible for running all processes
    they have PID 0 (process id 0)
    they are run by the root user
    There are several different init systems, and you should be aware
        of which one your distro is using as it will effect how you admin the box
    Systemd is the modern and probably most popular option
        the rest of this doc assumes systemd
    see also: https://www.computernetworkingnotes.com/linux-tutorials/differences-between-sysvinit-upstart-and-systemd.html

## Package managers

    There are many package managers that a distro might use.
    The 2 most popluar are RPM/YUM and DEB/APT.
    It's important to know which package manager your system uses so you will know how to install
    and update software.  

## Installing software

### Using Apt (debian, ubuntu)

    sudo apt update
    sudo apt upgrade
    apt search nginx
    sudo apt install nginx
    apt list
    apt list | grep nginx

### Using Yum (red hat, centos)

    sudo yum update
    sudo yum upgrade
    yum search nginx
    sudo yum install nginx
    yum list
    yum list | grep nginx


## Shells - Bash and Zsh

    https://learnxinyminutes.com/docs/bash/

    bash, zsh, macos
    chsh
    ~/.bash_profile, ~/.
    $PATH
    alias
    env
    export
    unset

## List running processes

    ps
    ps -ef
    top
    htop

## list enabled services

    systemctl list-unit-files
    systemctl status nginx
    systemctl enable 

## Find files

    find
    locate
    sudo updatedb

## Navigate file system

    cd
    cd ~
    pwd
    ls -la

    cd ..
    cd ../../
    cd /
    pushd
    popd

## important directories and files

    ~
    .
    ..
    /
    /etc
    /var
    /var/log
    /var/log/messages
    /opt
    /dev
    /usr/bin
    /usr/local/bin



## working with files

    ls
    cat
    grep
    cut
    awk
    vim
    https://learnxinyminutes.com/docs/vim/

## Block storage / attached disks

    lsblk
    du
    df
    mount
    /etc/fstab

## Networking basics

    ifconfig
    ip a
    systemctl status network

## Security

    selinux
    firewalld
    permissions
    chmod
    chown
    whoami
    su, sudo
