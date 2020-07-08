# Redhat

## RHCSA

### Understand and use essential tools
1. Access a shell prompt and issue commands with correct syntax
    * Common commands and their options, as well as vim usage, are shown below:
    
        | Command        | Options                                                                                                                                                          | Description                                     |
        |----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|
        | ls             | -h (human readable) <br>  -a (show hidden) <br> -l (detailed) <br> -lt (newist file first) <br> -ltr (oldest file first)                                         | List of files and directories                   |
        | pwd            |                                                                                                                                                                  | Print working directory                         |
        | cd             | ~ (home) <br> / (root) <br> - (switch) <br> .. (parent)                                                                                                          | Change directories                              |
        | who            | whoami (show user)                                                                                                                                               | Show logged in users                            |
        | what           | w (shorthand)                                                                                                                                                    | Show logged in users with more detail           |
        | uptime         |                                                                                                                                                                  | Show system uptime                              |
        | logname        |                                                                                                                                                                  | Show real username (if using su)                |
        | id             |                                                                                                                                                                  | Shows a user's UID, username, GUID etc.         |
        | groups         |                                                                                                                                                                  | Lists groups for users                          |
        | last           |                                                                                                                                                                  | List all user logins and system reboots         |
        | lastb          |                                                                                                                                                                  | List all failed login attempts                  |
        | lastlog        |                                                                                                                                                                  | List recent logins                              |
        | uname          | -a (details)                                                                                                                                                     | System information                              |
        | hostnamectl    | set-hostname                                                                                                                                                     | View hostname                                   |
        | clear          |                                                                                                                                                                  | Clear the screen                                |
        | timedatectl    | set-time <br> list-timezones <br> set-timezone <br>                                                                                                              | Display system time                             |
        | date           | --set                                                                                                                                                            | View system date                                |
        | which          |                                                                                                                                                                  | Show path to a command                          |
        | wc             |                                                                                                                                                                  | Word count                                      |
        | lspci          | -m (legible)                                                                                                                                                     | PCI buses details                               |
        | lsusb          |                                                                                                                                                                  | USB buses details                               |
        | lscpu          |                                                                                                                                                                  | Processor details                               |
        | gzip/bzip2     | -d (uncompress)                                                                                                                                                  | Compress files                                  |
        | gunzip/bunzip2 |                                                                                                                                                                  | Uncompress files                                |
        | tar            | -c (create) <br> -f (specifies name) <br> -v (verbose) <br> -r (append to existing) <br> -x (extract) <br> -z (compress with gzip) <br> -j (compress with bzip2) | Archive file                                    |
        | star           |                                                                                                                                                                  | Enhanced tar                                    |
        | man            | -k (keyword) <br> -f (short description)                                                                                                                         | Manual                                          |
        | mandb          |                                                                                                                                                                  | Update the mandb                                |
        | ssh            | -l (as different user)                                                                                                                                           | SSH to another Linux system                     |
        | tty            |                                                                                                                                                                  | Display terminal name                           |
        | whatis         |                                                                                                                                                                  | Search the command in the mandb for description |
        | info           |                                                                                                                                                                  | More detailed than man                          |
        | apropos        |                                                                                                                                                                  | Search the command in the mandb                 |
        | grep           | -n (show line numbers) <br> -v (pattern exclusion) <br> -i (case insensitive) <br> -E (use alternation) <br> -w (word match)                                     | Find text                                       |
        
        | Key                      | Description                     |
        |--------------------------|---------------------------------|
        | i                        | Change to insert mode           |
        | h, j, k, l               | Move left, down, up, right      |
        | w, b, e, ge              | Move word at a time             |
        | n[action]                | Do n times                      |
        | x                        | Remove a character              |
        | a                        | Append                          |
        | f[char]                  | Move to next given char in line |
        | F[char]                  | Move to previous char in line   |
        | ; and ,                  | Repeat last f or F              |
        | /yourtext and then: n, N | Search text                     |
        | d[movement]              | Delete by giving movement       |
        | r[char]                  | Replaces character below cursor |
        | 0, $                     | Move to start/end of line       |
        | o, O                     | Add new line                    |
        | %                        | Goto corresponding parentheses  |
        | ci[movement]             | Change inside of given movement |
        | D                        | Delete to end of line           |
        | S                        | Clear current line              |
        | gg / G                   | Move to start / end of buffer   |
        | yy                       | Copy current line               |
        | p                        | Paste copied text after cursor  |
    
1. Use input-output redirection (>, >>, |, 2>, etc.)
    * The default locations for input, output, and error are referred to as standard input (stdin), standard output (stdout), and standard error (stderr).
    * Standard input redirection can be done to have a command read the required information from an alternative source, such as a file, instead of the keyboard. For example:
    
        ```shell
        cat < /etc/cron.allow 
        ```
    * Standard output redirection sends the output generated by a command to an alternative destination, such as a file. For example:
    
        ```shell
        ll > ll.out
        ```
    * Standard error redirection sends the output generated by a command to an alternative destination, such as a file. For example: 
       
        ```shell
        echo test 2> outerr.out
        ```
    * Instead of > to create or overwrite, >> can be used to append to a file.
1. Use grep and regular expressions to analyze text
    * The grep command is used to find text. For example:
    
        ```shell
        grep user100 /etc/passwd
        ```    
    * Common regular expression parameters are shown below:
    
        | Symbol | Description                                                        |
        |--------|--------------------------------------------------------------------|
        | ^      | Beginning of a line or word                                        |
        | $      | End of a line or word                                              |
        | \|     | Or                                                                 |
        | .      | Any character                                                      |
        | *      | Any number of any character                                        |
        | ?      | Exactly one character                                              |
        | []     | Range of characters                                                |
        | \      | Escape character                                                   |
        | ''     | Mask meaning of enclosed special characters                        |
        | ""     | Mask meaning of all enclosed special characters except \, $ and '' |
    
1. Access remote systems using SSH

    * Secure Shell (SSH) provides a secure mechanism for data transmission between source and destination systems over IP networks.
    * SSH uses encryption and performs data integrity checks on transmitted data.
    * The version of SSH used is defined in */etc/ssh/sshd_config*.
    * The most common authentication methods are Password-Based Authentication and Public/Private Key-Based Authentication.
    * The command *ssh-keygen* is used to generate keys and place them in the .ssh directory, and the command *ssh-copy-id* is used to copy the public key file to your account on the remote server.
    * TCP Wrappers is a host-based mechanism that is used to limit access to wrappers-aware TCP services on the system by inbound clients. Two files */etc/hosts.allow* and */etc/hosts.deny* are used to control access. The .allow file is referenced before the .deny file. The format of the files is \<name of service process>:\<user@source>.
    * All messages related to TCP Wrappers are logged to the */var/log/secure* file.


1. Log in and switch users in multiuser targets

    * A user can switch to another user using the *su* command. The -i option ensures that the target users login scripts are run:

        ```shell
        sudo -i -u targetUser
        ``` 
    * To run a command as root without switching:
    
        ```shell
        sudo -c
        ``` 
    * The configuration for which users can run which commands using sudo is defined in the */etc/sudoers* file. The visudo command is used to edit the sudoers file. The sudo command logs successful authentication and command data to */var/log/secure*.

1. Archive, compress, unpack, and uncompress files using tar, star, gzip, and bzip2

    * To archive using tar:

        ```shell
        tar cvf myTar.tar /home
        ``` 

    * To unpack using tar:

        ```shell
        tar xvf myTar.tar
        ``` 

    * To compress using tar and gzip:

        ```shell
        tar cvfz myTar.tar /home
        ``` 

    * To compress using tar and bzip2:

        ```shell
        tar cvfj myTar.tar /home
        ``` 

    * To uncompress using tar and gzip:

        ```shell
        tar xvfz myTar.tar /home
        ``` 

    * To uncompress using tar and bzip2:

        ```shell
        tar xvfj myTar.tar /home
        ``` 

    * The star command is an enhanced versin of tar. It also supports SELinux security contexts and extended file attributes. The options are similar to tar.


1. Create and edit text files

    * To create an empty file:

        ```shell
        touch file
        cat > newfile
        ``` 

    * To create a vile using vim:
    
        ```shell
        vi file
        ``` 

1. Create, delete, copy, and move files and directories

    * To create a directory:

        ```shell
        mkdir directory
        ``` 

    * To move a file or directory:

        ```shell
        mv item1 item2
        ```     

    * To copy a file or directory:

        ```shell
        cp item1 item2
        ```     

    * To remove a file:

        ```shell
        rm file1
        ```

    * To remove an empty directory:

        ```shell
        rmdir directory
        ```

    * To remove a non-empty directory:

        ```shell
        rm -r directory
        ```

1. Create hard and soft links

    * A soft link associates one file with another. If the original file is removed the soft link will point to nothing. To create a softlink to file1:

        ```shell
        ln -s file1 softlink
        ``` 

    * A hard link associates multiple files to the same inode making them indistinguishable. If the original file is removed, you will still have access to the data through the linked file. To create a softlink to file1:

        ```shell
        ln file1 hardlink
        ``` 

1. List, set, and change standard ugo/rwx permissions

    * Permissions are set for the user, group and others. User is the owner of the file or the directory, group is a set of users with identical access defined in */etc/group*, and others are all other users. The types of permission are read, write and execute.
    * Permission combinations are shown below:

        | Octal Value | Binary Notation | Symbolic Notation | Explanation                           |
        |-------------|-----------------|-------------------|---------------------------------------|
        | 0           | 000             | ---               | No permissions.                       |
        | 1           | 001             | --x               | Execute permission only.              |
        | 2           | 010             | -w-               | Write permission only.                |
        | 3           | 011             | -wx               | Write and execute permissions.        |
        | 4           | 100             | r--               | Read permission only.                 |
        | 5           | 101             | r-x               | Read and execute permissions.         |
        | 6           | 110             | rw-               | Read and write permissions.           |
        | 7           | 111             | rwx               | Read, write, and execute permissions. |

    * To grant the owner, group and others all permissions using the *chmod* command:

        ```shell
        chmod 777 file1
        ```
    * The default permissions are calculated based on the umask. The default umask for root is 0022 and 0002 for regular users (the leading 0 has no significance). The pre-defined initial permissions are 666 for files and 777 for directories. The umask is subtracted from these initial permissions to obtain the default permissions. To change the default umask:

        ```shell
        umask 027
        ```
    * Every file and directory has an owner. By default, the creator assumes ownership. The owner's group is assigned to a file or directory. To change the ownership of a file or directory:

        ```shell
        useradd user100
        chown user100 item1
        chgrp user100 item1
        ```
    
        ```shell
        chown user100:user100 item1
        ```
    * Note that the -R option must be used to recusively change all files in a directory.

1. Locate, read, and use system documentation including man, info, and files in */usr/share/doc*

    * The *man* command can be used to view help for a command. To search for a command based on a keyword the *apropros* command or *man* with the -k option can be used. The *mandb* command is used to build the man database.

    * The *whatis* command can be used to search for a command in the man database for a short descripton.

    * The *info* command provides more detailed information than the *man* command. 

    * The */usr/share/doc* directory contains documentation for all installed packages under sub-directories that match package names followed by their version.

### Operate running systems

1. Boot, reboot, and shut down a system normally

    * The RHEL boot process occurs when the system is powered up or reset, and lasts until all enabled services are started and a login prompt appears at the screen. The login process consists of 4 steps:

        * The firmware is the Basic Input Output System (BIOS) or Unified Extensible Firmware Interface (UEFI) code that is stored in flash memory on the motherboard. The first thing it does is run the power-on-self-test (POST) to initialise the system hardware components. It also installs appropriate drivers for the video hardware and displays system messages to the screen. It scans the available storage devices to locate a boot device (GRUB2 on RHEL), and then loads it into memory and passes control to it.

        * The boot loader presents a menu with a list of bootable kernels available on the system. After a pre-defined amount of time it boots the default kernel. GRUB2 searches for the kernel in the */boot* file system. It then extracts the kernel code into memory and loads it based on the configuration in */boot/grub2/grub.cfg*. Note that for UEFI systems, GRUB2 looks in */boot/efi* instead and loads based on configuration in */boot/efi/EFI/redhat/grub.efi*. Once the kernel is loaded, GRUB2 passes control to it.

        * The kernel loads the initial RAM disk (initrd) image from the */boot* file system. This acts as a temporary file system. The kernal then loads necessary modules from initrd to allow access to the physical disks and the partitions and file systems within. It also loads any drivers required to support the boot process. Later, the kernal unmounts initrd and mounts the actual root file system.

        * The kernel continues the boot process. *systemd* is the default system initilisation scheme. It starts all enabled userspace system and network services.

    * The *shutdown* command is used to halt, power off, or reboot the system gracefully. This command broadcasts a warning message to all logged-in users, disables further user logins, waits for the specified time, and then stops the service and shuts to the system down to the specified target state. 
    
    * To shut down the system now:
        ```shell
        shutdown -P now
        ```

    * To halt the system now:
        ```shell
        shutdown -H now
        ```

    * To reboot the system now:
        ```shell
        shutdown -r now
        ```

    * To shut down the system after 5 minutes:
        ```shell
        shutdown -P 5
        ```

1. Boot systems into different targets manually

    * *systemd* is the default system initialisation mechanism in RHEL8. It is the first process that starts at boot and it is the last process that terminates at shutdown.

    * *Units* are systemd objects that are used for organising boot and maintenance tasks, such as hardware initialisation, socket creation, file system mounts, and service startups. Unit configuration is stored in their respective configuration files, which are auto-generated from other configurations, created dynamically from the system state, produced at runtime, or userdeveloped. Units are in one of several operational states, including active, inactive, in the process of being activated or deactivated, and failed. Units can be enabled or disabled.

    * Units have a name and a type, which are encoded in files of the form unitname.type. Units can be viewed using the *systemctl* command. A target is a logical collection of units. They are a special systemd unit type with the .target file extension.

    * *systemctl* is the primary command for interaction with systemd. 

    * To boot into a custom target the *e* key can be pressed at the GRUB2 menu, and the desired target specified using systemd.unit. After editing press *Ctrl+x* to boot into the target state. To boot into the emergency target: 
        ```shell
        systemd.unit=emergency.target
        ```

    * To boot into the rescue target:
        ```shell
        systemd.unit=rescue.target
        ```

    * Run *systemctl reboot* after you are done to reboot the system.

1. Interrupt the boot process in order to gain access to a system

    * Press *e* at the GRUB2 menu and add "rd.break" in place of "ro crash". 
    * Press *Ctrl+x* to reboot.
    * Run the following command to remount root with rw:
        ```shell
        mount -o remount,rw /sysroot
        ```
    *  Run the following command to change the root directory:
        ```shell
        chroot /sysroot
        ```
    *  Run *passwd* command to change the password.
    *  Run the following commands to create an empty, hidden file to instruct the system to perform SELinux relabeling after the next boot:
        ```shell
        touch /.autorelabel
        exit
        exit
        ```



1. Identify CPU/memory intensive processes and kill processes

1. Adjust process scheduling

1. Manage tuning profiles

1. Locate and interpret system log files and journals

1. Preserve system journals

1. Start, stop, and check the status of network services

1. Securely transfer files between systems


### Configure local storage

### Create and configure file systems

### Deploy, configure, and maintain systems

### Manage basic networking

### Manage users and groups

### Manage security