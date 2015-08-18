Oracle Solaris 11.2 vagrant Environment
====

Yuanzhen ZHOU <szrednick@gmail.com>
----

# Download and import the Oracle Solaris 11.2 vagrant box

## Download
```sh
wget -c http://www.benden.us/vagrant/solaris-11.2.box
```

## Import
```sh
$ vagrant box add solaris/11.2 ./unix/solaris-11.2.box

$ vagrant box list | grep solaris
solaris/11.2                      (virtualbox, 0)
```

# Run up the Solaris via vagrant
```sh
$ vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
==> default: Importing base box 'solaris/11.2'...
==> default: Matching MAC address for NAT networking...
==> default: Setting the name of the VM: solaris11.2dev
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
    default: Warning: Remote connection disconnect. Retrying...
    default:
    default: Vagrant insecure key detected. Vagrant will automatically replace
    default: this with a newly generated keypair for better security.
    default:
    default: Inserting generated public key within guest...
    default: Removing insecure key from the guest if it's present...
==> default: Machine booted and ready!
==> default: Checking for guest additions in VM...
    default: The guest additions on this VM do not match the installed version of
    default: VirtualBox! In most cases this is fine, but in rare cases it can
    default: prevent things such as shared folders from working properly. If you see
    default: shared folder errors, please make sure the guest additions within the
    default: virtual machine match the version of VirtualBox you have installed on
    default: your host and reload your VM.
    default:
    default: Guest Additions Version: 4.3.18
    default: VirtualBox Version: 5.0
==> default: Mounting shared folders...
    default: /vagrant => /ws/gogs/vabase/solaris11.2
    default: /opt/tools => /ws/gogs/vabase/solaris11.2/tools
==> default: Running provisioner: shell...
    default: Running: inline script
==> default: Hello world!:
```

# Use the new vagrant solaris env
```sh
$ vagrant ssh
Last login: Fri Jul 31 08:57:36 2015 from 10.0.2.2
Oracle Corporation      SunOS 5.11      11.2    June 2014
vagrant@solaris:~$
```
