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


## How to make apple's macos image preview like feature in ubuntu
```console
sudo apt-get update
sudo apt-get install gnome-sushi
```
