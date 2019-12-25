# SPDX-License-Identifier: GPL-2.0
dtbo-$(CONFIG_ARCH_ROCKCHIP) += \
	rk3399pro-i2c2.dtbo \
	rk3399pro-i2c6.dtbo \
	rk3399pro-i2c7.dtbo \
	rk3399pro-console-on-uart2.dtb \
	rk3399pro-console-on-uart4.dtb \
	rk3399pro-uart2.dtbo \
	rk3399pro-uart4.dtbo \
	rk3399pro-pwm0.dtbo \
	rk3399pro-pwm1.dtbo \
	rk3399pro-spi-spidev.dtbo

scr-$(CONFIG_ARCH_ROCKCHIP) += \
	rockchip-fixup.scr

dtbotxt-$(CONFIG_ARCH_ROCKCHIP) += \
	README.rockchip-overlays

targets += $(dtbo-y) $(scr-y) $(dtbotxt-y)

always			:= $(dtbo-y) $(scr-y) $(dtbotxt-y)
clean-files		:= *.dtbo *.scr

