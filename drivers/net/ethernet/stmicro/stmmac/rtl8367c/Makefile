RTL8367CCFLAGS += -g -Wall -Wstrict-prototypes -Dlinux -DLINUX -DMDC_MDIO_OPERATION -DBUILD_IN_KERNEL 

NETRTLFILES += acl.o cpu.o dot1x.o eee.o i2c.o igmp.o interrupt.o	\
	      l2.o leaky.o led.o mirror.o oam.o port.o ptp.o qos.o 	\
	      rate.o rldp.o rtk_switch.o rtl8367c_asicdrv.o rtl8367c_asicdrv_acl.o	\
	      rtl8367c_asicdrv_cputag.o rtl8367c_asicdrv_dot1x.o rtl8367c_asicdrv_eav.o \
	      rtl8367c_asicdrv_eee.o rtl8367c_asicdrv_fc.o rtl8367c_asicdrv_green.o \
	      rtl8367c_asicdrv_hsb.o rtl8367c_asicdrv_i2c.o rtl8367c_asicdrv_igmp.o \
	      rtl8367c_asicdrv_inbwctrl.o rtl8367c_asicdrv_interrupt.o rtl8367c_asicdrv_led.o \
	      rtl8367c_asicdrv_lut.o rtl8367c_asicdrv_meter.o rtl8367c_asicdrv_mib.o \
	      rtl8367c_asicdrv_mirror.o rtl8367c_asicdrv_misc.o rtl8367c_asicdrv_oam.o \
	      rtl8367c_asicdrv_phy.o rtl8367c_asicdrv_port.o rtl8367c_asicdrv_portIsolation.o \
	      rtl8367c_asicdrv_qos.o rtl8367c_asicdrv_rldp.o rtl8367c_asicdrv_rma.o \
	      rtl8367c_asicdrv_scheduling.o rtl8367c_asicdrv_storm.o rtl8367c_asicdrv_svlan.o \
	      rtl8367c_asicdrv_trunking.o rtl8367c_asicdrv_unknownMulticast.o rtl8367c_asicdrv_vlan.o \
	      smi.o stat.o storm.o svlan.o trap.o trunk.o vlan.o
	      
	      
EXTRA_CFLAGS += $(RTL8367CCFLAGS)
EXTRA_CFLAGS += -DSRCBASE=\"$(src)\"
EXTRA_CFLAGS += -I$(src)/
KBUILD_CFLAGS += -I$(LINUXDIR) -I$(shell pwd)

netrtl-objs := $(NETRTLFILES)

obj-$(CONFIG_ETHNET_RTL8367C) += netrtl.o
