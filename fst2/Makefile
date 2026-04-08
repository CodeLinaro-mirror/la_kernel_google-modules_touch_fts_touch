KERNEL_SRC ?= /lib/modules/$(shell uname -r)/build
M ?= $(shell pwd)

KBUILD_OPTIONS	+= CONFIG_TOUCHSCREEN_FST2=m
CFLAGS_MODULE	+= -DDYNAMIC_DEBUG_MODULE
CFLAGS_MODULE	+= -DCONFIG_TOUCHSCREEN_TBN
CFLAGS_MODULE	+= -DCONFIG_TOUCHSCREEN_HEATMAP
CFLAGS_MODULE	+= -DCONFIG_TOUCHSCREEN_OFFLOAD
CFLAGS_MODULE	+= -I$(KERNEL_SRC)/../google-modules/display
CFLAGS_MODULE	+= -I$(KERNEL_SRC)/../google-modules/touch/common
CFLAGS_MODULE	+= -I$(KERNEL_SRC)/../google-modules/touch/common/include
EXTRA_SYMBOLS	+= $(OUT_DIR)/../google-modules/touch/common/Module.symvers

modules modules_install clean:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) \
	$(KBUILD_OPTIONS) \
	CFLAGS_MODULE="$(CFLAGS_MODULE)" \
	KBUILD_EXTRA_SYMBOLS="$(EXTRA_SYMBOLS)" \
	$(@)
