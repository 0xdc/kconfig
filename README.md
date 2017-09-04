This repo contains Kconfig definitions to automatically select options for a kernel build tailored for my systems.

The Kconfig definitions won't be enabled without first enabling the META\_OPTIONS option. Options can be customised
or enabled completely with the META\_ALL option.

Quick start
===========

```
$ git clone https://github.com/0xdc/kconfig
$ cd kconfig
$ git remote add stable https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git
$ git fetch stable
$ git checkout -b linux-4.9.y master
$ git merge --allow-unrelated-histories -X ours stable/linux-4.9.y
$ make defconfig
$ ./build
# rsync -r meta/install.d/ /etc/kernel/install.d
# make modules_install
# kernel-install add $(make kernelrelease) arch/x86/boot/bzImage
```
