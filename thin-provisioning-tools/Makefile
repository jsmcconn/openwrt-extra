#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=thin-provisioning-tools
PKG_VERSION:=0.7.6
PKG_RELEASE:=1
PKG_LICENSE:=GPL-3.0

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/jthornber/thin-provisioning-tools.git
PKG_SOURCE_DATE:=2018-05-22
PKG_SOURCE_VERSION:=6a7351da0d3d1348a13752627d1f820acf34c42f
PKG_MIRROR_HASH:=1bc3c9e3e38f1f56d05a05b3dd8b412310ee6e118078da3d606cf389cbb94c0c
PKG_MAINTAINER:=Jeremiah McConnell <miah@miah.com>

PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk

define Package/thin-provisioning-tools
	SECTION:=utils
	CATEGORY:=Utilities
	SUBMENU:=Disc
	TITLE:=Tools for handling thinly provisioned device-mapper meta-data
	URL:=https://github.com/jthornber/thin-provisioning-tools
	DEPENDS:=@KERNEL_AIO +boost +libaio +libexpat
endef

define Package/thin-provisioning-tools/description
 This package contains tools to handle meta-data from the device-mapper thin
 target. This target allows the use of a single backing store for multple
 thinly provisioned volumes. Numerous snapshots can be taken from such volumes.
 The tools can check the meta-data for consistency, repair damaged information
 and dump or restore the meta-data in textual form.
endef

TARGET_BINDIR:=/usr/sbin

define Package/thin-provisioning-tools/install
	$(INSTALL_DIR) $(1)$(TARGET_BINDIR)
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/pdata_tools $(1)$(TARGET_BINDIR)
	$(STRIP) $(1)$(TARGET_BINDIR)/pdata_tools
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/cache_check
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/cache_dump
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/cache_metadata_size
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/cache_repair
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/cache_restore
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/cache_writeback
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/thin_check
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/thin_delta
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/thin_dump
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/thin_ls
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/thin_repair
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/thin_restore
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/thin_rmap
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/thin_metadata_size
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/thin_trim
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/era_check
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/era_dump
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/era_invalidate
	ln -s -f pdata_tools $(1)$(TARGET_BINDIR)/era_restore
endef

$(eval $(call BuildPackage,thin-provisioning-tools))

