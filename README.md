## What is a VM?

A virtual machine (VM) is a virtual environment that functions as a virtual computer system with its own CPU, memory, network interface, and storage, created on a physical hardware system, the resources of the machine are managed by a **hypervisor** which is a software that isolates the hypervisor’s operating system and resources from the VM and enables the creation and management of those VMs.

there are two main types of hypervisors:

- Type 1 (bare-metal)
    
    this type runs directly on the hardware without an OS, allowing the machine to provide more efficient and secure virtualization environment, it is widely used among enterprises. Examples of type 1 hypervisors include VMware ESXi, Microsoft Hyper-V, and Citrix XenServer.
    
- Type 2 (hosted)
    
    this type (as the name suggests) is hosted on an OS, in this case the host OS manages the hardware resources, and the hypervisor runs on top of it. Examples of type 2 hypervisors include VMware Workstation, Oracle VirtualBox, and VMware Fusion.
    

## Why using Debian?

- it has a large and active community of users and developers, which gives a lot of online resources and support.
- it is user-friendly and easy to use.
- the package management, it is easy to install, upgrade, and remove software packages.
- it is very stable and reliable.

## Rocky vs Debian:

### Debian:

it is a free open-source OS, developed and maintained by a community of volunteers, it is made mainly for individuals and personal use, it is known for its stability and reliability.

### Rocky:

it is an open-source enterprise OS, and it is a new replacement for CentOS, Rocky is based on Red Hat Enterprise Linux (RHEL), which is a commercial Linux distribution, it is often used in enterprise environment, and known for its security and performance. but it doesn’t run on as many architectures, unlike Debian that supports many packages.

- Package management: Debian uses the Advanced Packaging Tool (APT) for package management, while Rocky uses the Yellowdog Updater Modified (YUM) package manager.
- Supported architectures: Debian supports a wider range of architectures, including ARM, PowerPC, and MIPS, while Rocky only supports x86 and x86-64 architectures.

## Interest of VMs:

using a virtual machine, allows us to run more than one operating system on one device, which gives us an independent environment for experiments without affecting the main computer, also distributing the resources of a single computer to multiple people, also it lowers the costs of electricity and maintenance, and in the case of a failure, VMs can easily be transferred to another working machine.

## Apt vs Aptitude:

**apt-get** and **aptitude** are tools that handle package management, both are capable of handling all kinds of activities on packages including installation, removal search etc. Apart from main difference being that **Aptitude** is a high-level package manager while **APT** is lower-level package manager which can be used by other higher-level package managers, other main highlights that separate these two package managers are:

**Aptitude** is vaster in functionality than **apt-get** and integrates functionalities of apt-get and its other variants including **apt-mark** and **apt-cache**.

While **apt-get** handles all the package installation, up-gradation, system-upgradation, purging package, resolving dependencies etc., 

Aptitude handles lot more stuff than apt, including functionalities of **apt-mark** and **apt-cache** i.e. searching for a package in list of installed packages, marking a package to be automatically or manually installed, holding a package making it unavailable for up-gradation and so on.

## AppArmor:

it is a Linux Kernel security module, It allows you to specify which resources an application can access, such as network sockets, files, and other applications. This helps to protect the system and user data from malicious or poorly-written programs. AppArmor is implemented at the kernel level, so it is very effective at preventing unauthorized access to system resources. It is a Mandatory Access Control (MAC) system, which means that it enforces rules for all programs, regardless of whether or not the programs are written to be secure. This makes it effective at preventing even unknown vulnerabilities in programs from being exploited. AppArmor is included by default in many Linux distributions, and it can be used to increase the security of a system by limiting the abilities of potentially malicious programs.

## LVM:

*LVM*, or Logical Volume Management, is a storage device management technology that gives users the power to pool and abstract the physical layout of component storage devices for flexible administration.

LVM functions by layering abstractions on top of physical storage devices. The basic layers that LVM uses, starting with the most primitive, are:

- **Physical Volumes**:
    
    The LVM utility prefix for physical volumes is `pv`. This physically blocks devices or other disk-like devices (for example, other devices created by device mapper, like RAID arrays) and are used by LVM as the raw building material for higher levels of abstraction. Physical volumes are regular storage devices. LVM writes a header to the device to allocate it for management.
    
- **Volume Groups**:
    
    The LVM utility prefix for volume groups is `vg`. LVM combines physical volumes into [storage pools](https://www.ibm.com/docs/en/tsm/7.1.0?topic=volumes-storage-pools) known as volume groups. Volume groups abstract the characteristics of the underlying devices and function as a unified logical device with combined storage capacity of the component physical volumes.
    
- **Logical Volumes**:
    
    The LVM utility prefix for logical volumes is `lv`, generic LVM utilities might begin with `lvm`. A volume group can be sliced up into any number of logical volumes. Logical volumes are functionally equivalent to partitions on a physical disk, but with much more flexibility. Logical volumes are the primary component that users and applications will interact with.
    

LVM can be used to combine physical volumes into volume groups to unify the storage space available on a system. Afterwards, administrators can segment the volume group into arbitrary logical volumes, which act as flexible partitions.

here are some advantages of LVM:

1. Flexibility: LVM allows you to create, resize, and delete logical volumes without having to recreate partitions or reformat the disk. This makes it easier to adapt to changing storage needs.
2. Performance: LVM allows you to stripe data across multiple disks, which can improve performance by distributing the workload across multiple disks.
3. Snapshots: LVM allows you to create snapshots of logical volumes, which can be useful for backing up data or rolling back changes.
4. Multiple Operating Systems: LVM allows you to create logical volumes that can be shared by multiple operating systems, making it easier to dual-boot or run multiple operating systems on a single machine.
5. Disk Replacement: LVM allows you to easily replace failed disks or add additional disks to a volume group without having to recreate partitions or reformat the disks.

## Sudo:

In order for a given user to execute a command as the superuser (root) or another user, there are two ways,

the first one is to log in as the root user permanently, but anyone else who can access the computer can accuire the permissions,

the second is to use the sudo command which is a Unix-based command that stands for “super user do” that elevates your permissions for a short time to execute the command that you need.

### how does sudo work?

### what about the su ?

The su is a standalone command that lets you change which user’s privileges sudo elevates you to.

## UFW(uncomplicated firewall):

first of all, what is a firewall? a firewall is a network security system that controls and monitors incoming and outgoing network traffic, based on predetermined security rules.

UFW (Uncomplicated Firewall) is a frontend for the **`iptables`** utility on Linux systems. it operates by modifying the **`iptables`** rules that are stored in the kernel. It allows you to specify which types of network traffic should be allowed or denied, based on various criteria such as the source and destination IP address, port number, and protocol.

- **iptables:**
    
    it is a command-line utility that allows you to configure the firewall on a Linux system (Netfilter). It is used to set up, maintain, and inspect the tables of IP packet filter rules in the Linux kernel.
    
    Using **`iptables`**, you can specify rules to allow or block incoming or outgoing network traffic based on various criterias, such as the source or destination IP address, the protocol, or the port number. You can also use **`iptables`** to NAT (Network Address Translation) packets, redirect traffic, or log dropped packets.
    
- **ports:**
    
    A port is a logical connection that is used by programs and services to exchange informations, every port has it’s own unique number that will be used to identifie it, it ranges from 0 to 65535, for example:
    
    - 80, 443 is for Web pages (HTTP, HTTPS)
    - 21, FTP (file transfer protocol)
    - 25, Email (SMTP)
    
    the port number is always associated with an IP address, which is an identifier for a computer or device in a given network, the port number and the IP adress work together to exchange data on an address, and together they form what’s called a socket.
    
- **protocol**
    
    A protocol defines the format and the order of messages exchanged between two or more
    communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other events.
    

## SSH(secure shell):

SSH or **Secure Shell** is a **remote administration protocol that allows users to control and modify their servers over the Internet** thanks to an authentication mechanism. SSH was created as an alternative to Telnet, which does not encrypt the information that is sent.

There are three different techniques that SSH uses to encrypt:

- **Symmetric encryption:** a method that uses the same secret key for both encryption and decryption of a message, for both the client and the host. Anyone who knows the password can access the message that has been transmitted.
- **Asymmetric encryption:** uses two separate keys for encryption and decryption. These are known as the public key and the private key. Together, they form the public-private key pair.
- **Hashing:** another form of cryptography used by SSH. Hash functions are made in a way that they don't need to be decrypted. If a client has the correct input, they can create a cryptographic hash and SSH will check if both hashes are the same.

During the SSH handshake, the client and server exchange public keys and a message authentication code (MAC). The MAC is a hash of the shared secret key and the message being transmitted, and it is used to verify the integrity of the message. This helps to ensure that the message has not been tampered with or altered in transit.

# Cron:

It is a Unix utility that is used to schedule commands for automatic execution at a specefic time or interval, the tasks (cron jobs) are defined in a crontab(cron tables) file, which contains the commands to be executed and their schedules.

it is a daemon process, which means it keeps runing in the background.

# Wordpress:

WordPress is a free and open-source content management system written in hypertext preprocessor language and paired with a MySQL or MariaDB database with supported HTTPS.

- Mariadb
    
    it is a free and open-source database management system, and it is a fork of the MySQL database system.
    
- Lighttpd
    
    it is an open-source web service optimized for speed and low memory usage.
    
    - Web server
     It can refer to hardware or software, or both of them working together.
        - On the hardware side, a web server is a computer that stores web server software and a website's component files (for example, HTML documents, images, CSS stylesheets, and JavaScript files).
        - On the software side, a web server includes several parts that control how web users access hosted files. At a minimum, this is an HTTP server. which is a software that understands URLs (web addresses) and HTTP (the protocol your browser uses to view webpages).
       
# Proxy:

it is a server or a computer system that acts as a gateaway between users and the internet, Proxies are used to improve security, increase performance, and enable access to resources that may be restricted or blocked in certain regions.

there are many types of proxies:

- Reverse proxies: These are used to receive client requests and forward them to one or more servers. Reverse proxies are often used to balance load among multiple servers, improve security by hiding the origin server, and cache static content for faster access.
- Forward proxies: These are used by clients to access servers and resources on behalf of the client. Forward proxies are often used to access websites or servers that are blocked in a particular region, or to mask the client's IP address to protect their privacy.
- Transparent proxiest(the one I did): These are used to intercept and modify client requests without the client's knowledge. Transparent proxies are often used to filter or censor internet content, or to redirect client requests to different servers.
- Anonymous proxies: These are used to mask the client's IP address and protect their identity and location. Anonymous proxies do not reveal the client's IP address to the server.

## Resources:

[What is the difference between dpkg and aptitude/apt-get? - Ask Ubuntu](https://askubuntu.com/questions/309113/what-is-the-difference-between-dpkg-and-aptitude-apt-get)

[https://www.youtube.com/watch?v=UBVVq-xz5i0&t=392s](https://www.youtube.com/watch?v=UBVVq-xz5i0&t=392s)

[https://helpdeskgeek.com/linux-tips/what-is-sudo-in-linux-and-how-to-use-it/](https://helpdeskgeek.com/linux-tips/what-is-sudo-in-linux-and-how-to-use-it/)

[https://www.youtube.com/watch?v=g2fT-g9PX9o](https://www.youtube.com/watch?v=g2fT-g9PX9o)

[https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server)

[https://www.fortinet.com/resources/cyberglossary/proxy-server](https://www.fortinet.com/resources/cyberglossary/proxy-server)
