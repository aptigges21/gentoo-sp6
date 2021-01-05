## Kernel config file for Surface Pro 6 running Gentoo Linux

##### My current setup:

- Surface Pro 6 i5-8250U (Kaby-Lake R)
- OpenRC
- GCC 10.2
- [Full system LTO]( https://github.com/InBetweenNames/gentooLTO )
- Btrfs (hopefully snapshot support in grub soon)
- No-Multilib profile (32 bit instruction emulation disabled in kernel)
- suckless setup (dwm, st, etc.)
- Current kernel version -- 5.10.4-gentoo (~amd64) with
  [linux-surface patchset](https://github.com/linux-surface/linux-surface).
  Patching can be achieved by cloning the repository and running:
  ```
  for i in [linux-surface-repo]/patches/5.10/*.patch; do patch -p1 < $i; done
  ```

##### For kernel 5.10.4:
Applying the patches to 5.10.4 leads to conflicts. I replied no to each (default option)
and have not had problems yet.

##### Notes:
I am considering compiling a tutorial for
installing Gentoo on surface products
and, to this end, will be glad to answer any questions
you may have to the best of my ability (which will
most likely be me trying to figure it out with you :D).

This is a work in progress and some functionality
that you may expect could be disabled.
For now, this should only be considered a starting point.
