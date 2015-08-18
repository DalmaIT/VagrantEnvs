FreeBSD 11 vagrant Environment
====

Yuanzhen ZHOU <szrednick@gmail.com>
----

# Download and import the freebsd-11 vagrant box

## Download
```sh
wget -c http://www.benden.us/vagrant/freebsd-11.box
```

## Import
```sh
$ vagrant box add freebsd/11 freebsd-11.box

$ vagrant box list | grep bsd
freebsd/11                        (virtualbox, 0)
```

# Run up our freebsd via vagrant
```sh
$ vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
==> default: Importing base box 'freebsd/11'...
==> default: Matching MAC address for NAT networking...
==> default: Setting the name of the VM: freebsd11dev
==> default: Clearing any previously set network interfaces...
==> default: Preparing network interfaces based on configuration...
    default: Adapter 1: nat
==> default: Forwarding ports...
    default: 22 => 2222 (adapter 1)
==> default: Running 'pre-boot' VM customizations...
==> default: Booting VM...
==> default: Waiting for machine to boot. This may take a few minutes...
    default: SSH address: 127.0.0.1:2222
    default: SSH username: vagrant
    default: SSH auth method: private key
    default: Warning: Connection timeout. Retrying...
    default: Warning: Connection timeout. Retrying...
    default:
    default: Vagrant insecure key detected. Vagrant will automatically replace
    default: this with a newly generated keypair for better security.
    default:
    default: Inserting generated public key within guest...
    default: Removing insecure key from the guest if it's present...
    default: Key inserted! Disconnecting and reconnecting using new SSH key...
==> default: Machine booted and ready!
==> default: Checking for guest additions in VM...
    default: The guest additions on this VM do not match the installed version of
    default: VirtualBox! In most cases this is fine, but in rare cases it can
    default: prevent things such as shared folders from working properly. If you see
    default: shared folder errors, please make sure the guest additions within the
    default: virtual machine match the version of VirtualBox you have installed on
    default: your host and reload your VM.
    default:
    default: Guest Additions Version: 4.3.8
    default: VirtualBox Version: 5.0
==> default: Running provisioner: shell...
    default: Running: inline script
==> default: Hello world!:
```

# Use the new vagrant freebsd env
```sh
$ vagrant ssh
Last login: Sun Mar  9 13:30:20 2014
FreeBSD 11.0-CURRENT (GENERIC) #0 r262657: Sat Mar  1 19:48:00 UTC 2014

Welcome to FreeBSD!

Before seeking technical support, please use the following resources:

o  Security advisories and updated errata information for all releases are
   at http://www.FreeBSD.org/releases/ - always consult the ERRATA section
   for your release first as it's updated frequently.

o  The Handbook and FAQ documents are at http://www.FreeBSD.org/ and,
   along with the mailing lists, can be searched by going to
   http://www.FreeBSD.org/search/.  If the doc package has been installed
   (or fetched via pkg install lang-freebsd-doc, where lang is the
   2-letter language code, e.g. en), they are also available formatted
   in /usr/local/share/doc/freebsd.

If you still have a question or problem, please take the output of
`uname -a', along with any relevant error messages, and email it
as a question to the questions@FreeBSD.org mailing list.  If you are
unfamiliar with FreeBSD's directory layout, please refer to the hier(7)
manual page.  If you are not familiar with manual pages, type `man man'.

Edit /etc/motd to change this login announcement.

$ sudo su -
root@freebsd-11:~ # 
```
