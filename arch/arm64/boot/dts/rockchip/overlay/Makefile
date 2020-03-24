# SPDX-License-Identifier: GPL-2.0
dtbo-$(CONFIG_ARCH_ROCKCHIP) += \
	rk3399pro-console-on-uart2.dtbo \
	rk3399pro-console-on-uart4.dtbo \
	rk3399pro-i2c2.dtbo \
	rk3399pro-i2c4.dtbo \
	rk3399pro-i2c6.dtbo \
	rk3399pro-i2c7.dtbo \
	rk3399pro-i2c8.dtbo \
	rk3399pro-pcie-gen2.dtbo \
	rk3399pro-pwm0.dtbo \
	rk3399pro-pwm1.dtbo \
	rk3399pro-raspberrypi-7-inch-lcd.dtbo \
	rk3399pro-spi-spidev.dtbo \
	rk3399pro-uart2.dtbo \
	rk3399pro-uart4.dtbo \
	rk3399pro-w1-gpio.dtbo \
	spi1-flash-boot.dtbo

scr-$(CONFIG_ARCH_ROCKCHIP) += \
	rockchip-fixup.scr

dtbotxt-$(CONFIG_ARCH_ROCKCHIP) += \
	README.rockchip-overlays

targets += $(dtbo-y) $(scr-y) $(dtbotxt-y)

always			:= $(dtbo-y) $(scr-y) $(dtbotxt-y)
clean-files		:= *.dtbo *.scr

