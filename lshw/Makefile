#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lshw
PKG_VERSION:=B.02.18-git
PKG_RELEASE:=1
PKG_LICENSE:=GPL-2.0

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/lyonel/lshw.git
PKG_SOURCE_DATE:=2018-06-09
PKG_SOURCE_VERSION:=8486d25cea9b68794504fbd9e5c6e294bac6cb07
PKG_MIRROR_HASH:=7d7e0e84503a583b935d53a20ccac72c12ec209594d6ae0942fc29373a14b2ea
PKG_MAINTAINER:=Jeremiah McConnell <miah@miah.com>

include $(INCLUDE_DIR)/package.mk

define Package/lshw
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=display hardware configuration
	URL:=http://lshw.ezix.org
	DEPENDS:=+zlib +libstdcpp
endef

define Package/lshw/description
 lshw is a small tool to provide detailed information on the hardware
 configuration of the machine. It can report exact memory configuration,
 firmware version, mainboard configuration, CPU version and speed, cache
 configuration, bus speed, etc. on DMI-capable x86 or EFI (IA-64) systems
 and on some ARM and PowerPC machines (PowerMac G4 is known to work).

 Information can be output in plain text, XML or HTML.

 It currently supports DMI (x86 and EFI only), OpenFirmware device tree
 (PowerPC only), PCI/AGP, ISA PnP (x86), CPUID (x86), IDE/ATA/ATAPI, PCMCIA
 (only tested on x86), USB and SCSI.
endef

define Build/Compile
	$(call Build/Compile/Default,ZLIB=1)
endef

define Package/lshw/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/lshw $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,lshw))

