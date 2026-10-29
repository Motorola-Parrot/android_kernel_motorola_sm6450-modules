KBUILD_OPTIONS += CTS_MULTI_TP_MODULE_EN=y
KBUILD_OPTIONS += TOUCHSCREEN_PM_BRL_SPI=y
KBUILD_OPTIONS += CONFIG_INPUT_CHIPONE_0FLASH_MMI_NOTIFY_TOUCH_STATE=y

all: modules

modules:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) modules $(KBUILD_OPTIONS)

modules_install:
	$(MAKE) INSTALL_MOD_STRIP=1 -C $(KERNEL_SRC) M=$(M) modules_install

%:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) $@ $(KBUILD_OPTIONS)

clean:
	rm -f *.o *.ko *.mod.c *.mod.o *~ .*.cmd Module.symvers
	rm -rf .tmp_versions

KBUILD_EXTRA_SYMBOLS += $(M)/../../../mmi_info/$(GKI_OBJ_MODULE_DIR)/Module.symvers
KBUILD_EXTRA_SYMBOLS += $(M)/../touchscreen_mmi/$(GKI_OBJ_MODULE_DIR)/Module.symvers
KBUILD_EXTRA_SYMBOLS += $(M)/../../../../../qcom/opensource/display-drivers/msm/Module.symvers
