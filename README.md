# CrunkTools
A bunch of useful Linux scripts. I have quite a few more that I'll be adding after I do a little cleanup of the code. These are scripts that could be useful in a server environment.

## watchFreeSpace
![screenshot](https://github.com/kristoffer-marshall/CrunkTools/raw/master/screenshots/watchFreeSpace.png)

Allows one to watch the fluctuation of free space on a system. Flags are not yet supported. What you don't see in the example is that the output is colorized, so imagine green lines when space has been freed and red for used space.

EXAMPLE:
```
[xtoff@crunk CrunkTools]$ ./watchFreeSpace 
Delay between polls is 10. We're watching /home
8163 MB free, 93%
No changes                 8163 MB free, 93%
- 83 MB has been used      8080 MB free, 93%
- 83 MB has been used      7997 MB free, 93%
+ 166 MB has been freed    8163 MB free, 93%
No changes                 8163 MB free, 93%
No changes                 8163 MB free, 93% 
```

## findPHPVersions
This is an admittedly crude script to go through the filesystem and find all versions of PHP that exist. This is useful to find where pre-compiled PHP interpreters that exist in packaged appliations.

## reportFreeSpaceToUsers
This script finds large files in /home and emails the offending users with a list of their largest files. This script can save you plenty of headaches when space is low. This script will work assuming the names of the user directories directly correspond to an email address.

## rmblanklines
Remove blank lines from input.

USAGE EXAMPLE: cat file | rmblanklines

## rmspaces
Remove spaces from input.

USAGE EXAMPLE: cat file | rmspaces

## snmpBrute
A tool to brute force a SNMP query string.

USAGE: snmpBrute [-v] HOSTNAME STRINGFRAGMENT

## testConnection
This script will continuously attempt to open a TCP connection to the specified host and port. When the connection succeeds, an email will be sent out and the program will terminate. This is especially useful in an environment where someone else is doing your network change, or if you're testing something out and don't want to waste time actively watching a server.

## toCSV
Takes a filename as an argument and turns each newline to a comma.

## usedSpace
This script will go and find large files on the specified filesystem, then report back the largest files it had found in a nice looking format. Admittedly, I no longer remember where I got the perl code from, but here it is, slightly modified. The default minimum size it will report right now is 100MB, but that can be easily modified.

EXAMPLE:
```
[kris@crunk CrunkTools]$ ./usedSpace /home
  4.3	G	   **********************  /home/kris/VirtualBox VMs/lucy/lucy-disk1.vmdk
  4.3	G	   **********************  /home/kris/VirtualBox VMs/lucy/lucy-disk1_1.vmdk
939.4	M	     ********************  /home/kris/Pictures/weddingpics2.zip
779.5	M	     ********************  /home/kris/Pictures/weddingpics1.zip
263.6	M	       ******************  /home/kris/kvm/junos/junos-vsrx-12.1X47-D20.7-domestic-1425440825/junos-vsrx-12.1X47-D20.7-domestic.img
259.1	M	       ******************  /home/kris/Downloads/unsorted/fedora-23-remix-rpi2-minimal-1.raw.xz
225.0	M	       ******************  /home/kris/virtualmachines/junos-vsrx/junos-vsrx-12.1X47-D20.7-domestic-disk1.vmdk
222.5	M	       ******************  /home/kris/kvm/junos/junos-vsrx-12.1X47-D20.7-domestic.jva
211.4	M	       ******************  /home/kris2/Dropbox/sounds/hydrogen/libraries/BigMono.tar
196.3	M	       ******************  /home/kris/sounds/startrek.zip
```

## watchPort
This script will continuously attempt to open a TCP connection to the specified host and port. When the connection succeeds, an email will be sent out. This is especially useful in an environment where someone else is doing your network change, if you're testing something out, or if you want to watch the state of a service or tunnel.

## fixImages
This script will go through the current working directory and will locate some common image files. If the extension is non-existant or wrong, the script will fix it.

## whoisDomains
Give this a script a filename with a bunch of domain names or enter domains line by line (then CTRL + D). The script will go through and try to determine if the domain is registered or not via whois and will report "example.com is taken." if the domain is in fact registered.


