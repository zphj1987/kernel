# Overlays for the ROCK PI S platform

dtbo-$(CONFIG_ARCH_ROCKCHIP) += \
	console-on-ttyS2.dtbo

targets += dtbs dtbs_install
targets += $(dtbo-y)

always		:= $(dtbo-y)
clean-files	:= *.dtbo
