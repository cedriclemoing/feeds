#
# Copyright (C) 2006-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=bittwist-linux

PKG_VERSION:=2.0
PKG_RELEASE:=1
PKG_MD5SUM:=8a93e0ae5df3172dabf154ccfd31c49f

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=@SF/$(PKG_NAME)

PKG_MAINTAINER:=TODO
PKG_LICENSE:=GPLv2
PKG_LICENSE_FILES:=COPYING

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/bittwist
  SECTION:=net
  CATEGORY:=Network
  DEPENDS:=+libpcap
  TITLE:=TODO
  URL:=http://bittwist.sourceforge.net/
endef

define Package/bittwist/description
Bit-Twist is a simple yet powerful libpcap-based Ethernet packet generator. It is designed to complement tcpdump, which by itself has done a great job at capturing network traffic.
endef

MAKE_FLAGS += \
	prefix="$(PKG_INSTALL_DIR)"

define Package/bittwist/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/bin/bittwist $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/bin/bittwiste $(1)/usr/bin/
endef

$(eval $(call BuildPackage,bittwist))
