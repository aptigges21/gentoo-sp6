## Kernel config file for Surface Pro 6 running Gentoo Linux

#### My current setup:

- Surface Pro 6 i5-8250U (Kaby-Lake R)
- OpenRC
- GCC 10.2
- [Full system LTO]( https://github.com/InBetweenNames/gentooLTO )
- Btrfs (hopefully snapshot support in grub soon)
- No-Multilib profile (32 bit instruction emulation disabled in kernel)
- suckless setup (dwm, st, etc.)
- Current kernel version -- 5.10.7-gentoo (~amd64) with
  [linux-surface patchset](https://github.com/linux-surface/linux-surface).
  Patching can be achieved by cloning the repository and running:
  ```
  for i in [linux-surface-repo]/patches/5.10/*.patch; do patch -p1 < $i; done
  ```
#### Notes:
I am considering compiling a tutorial for
installing Gentoo on surface products
and, to this end, will be glad to answer any questions
you may have to the best of my ability (which will
most likely be me trying to figure it out with you :D).

This is a work in progress and some functionality
that you may expect could be disabled.
For now, this should only be considered a starting point.

#### Patch Script:
I am cerainly not a bash script expert but here is my first attempt 
at simplifying the patching process (suggestions welcome!).
For now this is only useful when moving to a new kernel version.

Using:
- Place the shell script in your `/usr/src` folder
- Edit the dir variable in the script to be the location of where you store the linux-surface patchset -- the script will perform a git pull automatically each time run
- Make sure it is executable using `chmod +x surface-patch` if necessary
- Run with ./surface-patch

On the current kernel I gave the following input:
```
Patch version?
# 5.10
Old kernel version?
# 10.6
New kernel version?
# 10.7
```
Then in `/usr/src/linux` perform `make -j8 && make -j8 modules_install && make install`
