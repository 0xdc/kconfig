This repo contains Kconfig definitions to automatically select options for a kernel build tailored for my systems.

The Kconfig definitions won't be enabled without first enabling the META\_OPTIONS option. Options can be customised
or enabled completely with the META\_ALL option.

Quick start
===========

```
$ git clone https://github.com/0xdc/kconfig
$ cd kconfig
$ git remote add stable https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git
$ git fetch stable linux-5.15.y
$ git checkout -b linux-5.15.y master
$ git merge --no-stat --allow-unrelated-histories -X ours stable/linux-5.4.y -m "Merge linux-5.15.y"
$ ./config
$ ./build
# rsync -r meta/install.d/ /etc/kernel/install.d
# make modules_install
# kernel-install add $(make kernelrelease) arch/x86/boot/bzImage
```
