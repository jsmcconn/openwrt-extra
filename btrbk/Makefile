#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=btrbk
PKG_VERSION:=0.26.1
PKG_RELEASE:=1
PKG_LICENSE:=GPL-3.0

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/digint/btrbk.git
PKG_SOURCE_DATE:=2018-03-05
PKG_SOURCE_VERSION:=1fd3a547df825ed369df8ded1bd9e4bf3b959627
PKG_MIRROR_HASH:=57fb2533eda238e466a7ce7a5601878a4fddf8700fd47c99429577ac9771ea85
PKG_MAINTAINER:=Jeremiah McConnell <miah@miah.com>

include $(INCLUDE_DIR)/package.mk

define Package/btrbk
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=Tool for creating snapshots and remote backups of btrfs subvolumes
	URL:=https://github.com/digint/btrbk
	DEPENDS:=+perl
endef

define Package/btrbk/description
 btrbk is a backup tool for btrfs subvolumes, taking advantage of btrfs
 specific capabilities to create atomic snapshots and transfer them
 incrementally to your backup locations.
endef

define Build/Compile
endef

define Package/btrbk/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/btrbk $(1)/usr/bin
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/btrbk.conf.example $(1)/etc
endef

define Package/btrbk/conffiles
/etc/btrbk.conf
endef

$(eval $(call BuildPackage,btrbk))

