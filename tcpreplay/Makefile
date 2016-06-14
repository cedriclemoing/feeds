#
# Copyright (C) 2006-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=tcpreplay
https://github.com/appneta/tcpreplay/releases/download/v4.1.1/tcpreplay-4.1.1.tar.gz
PKG_VERSION:=4.1.1
PKG_RELEASE:=1
PKG_MD5SUM:=80394c33fe697b53b69eac9bb0968ae9

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=@SF/$(PKG_NAME)

PKG_MAINTAINER:=TODO
PKG_LICENSE:=GPLv3
PKG_LICENSE_FILES:=COPYING

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk


CONFIGURE_ARGS += \
	--with-libpcap="$(STAGING_DIR)/usr"

define Package/tcpreplay
  SECTION:=net
  CATEGORY:=Network
  DEPENDS:=+libpcap +librt
  TITLE:=TODO
  URL:=http://tcpreplay.appneta.com/
endef

define Package/tcpreplay/description
Tcpreplay is a suite of free Open Source utilities for editing and replaying previously captured network traffic. Originally designed to replay malicious traffic patterns to Intrusion Detection/Prevention Systems, it has seen many evolutions including capabilities to replay to web servers.
endef

MAKE_FLAGS += \
	prefix="$(PKG_INSTALL_DIR)"

define Package/tcpreplay/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) ${PKG_BUILD_DIR}/src/tcpprep  $(1)/usr/bin/
	$(INSTALL_BIN) ${PKG_BUILD_DIR}/src/tcprewrite $(1)/usr/bin/
	$(INSTALL_BIN) ${PKG_BUILD_DIR}/src/tcpreplay $(1)/usr/bin/
	$(INSTALL_BIN) ${PKG_BUILD_DIR}/src/tcpliveplay $(1)/usr/bin/
	$(INSTALL_BIN) ${PKG_BUILD_DIR}/src/tcpreplay-edit $(1)/usr/bin/
	$(INSTALL_BIN) ${PKG_BUILD_DIR}/src/tcpbridge $(1)/usr/bin/
	$(INSTALL_BIN) ${PKG_BUILD_DIR}/src/tcpcapinfo $(1)/usr/bin/
endef

$(eval $(call BuildPackage,tcpreplay))
