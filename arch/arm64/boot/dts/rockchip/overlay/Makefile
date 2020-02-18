# SPDX-License-Identifier: GPL-2.0
dtbo-$(CONFIG_ARCH_ROCKCHIP) += \
	rk3308-i2c0.dtbo \
	rk3308-i2c1.dtbo \
	rk3308-i2c2.dtbo \
	rk3308-i2c3.dtbo \
	rk3308-uart0.dtbo \
	rk3308-uart1.dtbo \
	rk3308-uart2.dtbo \
	rk3308-pwm1.dtbo \
	rk3308-pwm2.dtbo \
	rk3308-pwm3.dtbo \
	rk3308-console-on-uart0.dtbo \
	rk3308-console-on-uart1.dtbo \
	rk3308-console-on-uart2.dtbo \
	rk3308-spi-spidev.dtbo \
	rk3308-w1-gpio.dtbo \
	rockpis-spi2-waveshare35b-v2.dtbo \
	rockpis-spi2-waveshare35c.dtbo

scr-$(CONFIG_ARCH_ROCKCHIP) += \
	rockchip-fixup.scr

dtbotxt-$(CONFIG_ARCH_ROCKCHIP) += \
	README.rockchip-overlays

targets += $(dtbo-y) $(scr-y) $(dtbotxt-y)

always			:= $(dtbo-y) $(scr-y) $(dtbotxt-y)
clean-files		:= *.dtbo *.scr

