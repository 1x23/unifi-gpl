#
# Makefile for USB Core files and filesystem
#

usbcore-objs	:= usb.o hub.o hcd.o urb.o message.o \
			config.o file.o buffer.o sysfs.o devio.o notify.o

ifeq ($(CONFIG_PCI),y)
	usbcore-objs	+= hcd-pci.o
endif

ifeq ($(CONFIG_USB_DEVICEFS),y)
	usbcore-objs	+= inode.o devices.o
endif

obj-$(CONFIG_USB)	+= usbcore.o

ifeq ($(CONFIG_USB_DEBUG),y)
EXTRA_CFLAGS += -DDEBUG
endif

ifdef AP_USB_LED_GPIO
CFLAGS_hub.o += -DAP_USB_LED_GPIO
endif
