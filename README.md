# some-commands-for-ubuntu-20.04

## How to increase swap memory:
Source[https://arcolinux.com/how-to-increase-the-size-of-your-swapfile/]  

Turn off all swap processes
```console
sudo swapoff -a
```
Resize the swap (from 512 MB to 8GB)  
```console
sudo dd if=/dev/zero of=/swapfile bs=1G count=8
```
if = input file  
of = output file  
bs = block size  
count = multiplier of blocks  

    
Make the file usable as swap

```console
sudo mkswap /swapfile
```
Activate the swap file

```console
sudo swapon /swapfile
```
Check the amount of swap available

```console
grep SwapTotal /proc/meminfo
```

## To add a path to linux environment variable:
### Add it to your ~/.profile or ~/.bashrc file. 

```console
export PATH="$PATH:/path/to/dir"
```

to create symlink to binaries:
```console
cd /usr/bin
sudo ln -s /path/to/binary binary-name
```

This will not automatically update your path for the remainder of the session. To do this, you run:

```console
source ~/.profile
```
or
```console
source ~/.bashrc
```

## How to make apple's macos image preview like feature in ubuntu
```console
sudo apt-get update
sudo apt-get install gnome-sushi
```

## To extract integers from a string

```console
import re
s = "checking skr (2, 3, 4, 6, -2, 12)"
#Find all integers (including negative numbers)
numbers = list(map(int, re.findall(r'-?\d+', s)))
```
re.findall(r'-?\d+', s):
\d+ matches one or more digits.
-? optionally matches a minus sign (for negative numbers).
map(int, ...) converts all matched strings to integers.
list(...) converts the map object to a list.
