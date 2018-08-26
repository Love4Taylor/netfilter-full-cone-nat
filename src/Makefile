obj-m := xt_FULLCONENAT.o
KERNEL_VERSION := $(shell uname -r)
IDIR := /lib/modules/$(KERNEL_VERSION)/kernel/net/netfilter/
KDIR := /lib/modules/$(KERNEL_VERSION)/build
DESTDIR ?= /
PWD := $(shell pwd)
VERSION := $(shell git rev-parse HEAD 2>/dev/null)
default:
	    $(MAKE) -C $(KDIR) SUBDIRS=$(PWD) modules

install:
	    $(MAKE) -C $(KDIR) SUBDIRS=$(PWD) INSTALL_MOD_PATH=$(DESTDIR) modules_install

clean:
	    rm -rf Module.markers modules.order Module.symvers xt_FULLCONENAT.ko xt_FULLCONENAT.mod.c xt_FULLCONENAT.mod.o xt_FULLCONENAT.o

