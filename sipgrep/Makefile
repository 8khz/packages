#
# Copyright (C) 2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=sipgrep
PKG_VERSION:=2.2.0
PKG_RELEASE:=1
PKG_REV:=df8a95b066569be92aa38cad01086ea595b36863
PKG_INSTALL:=1
PKG_FIXUP:=autoreconf libtool

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/sipcapture/sipgrep.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_SUBDIR:=$(PKG_NAME)

PKG_BUILD_DIR=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/$(PKG_NAME)
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Telephony
  TITLE:=SIPGREP - Display and Troubleshoot SIP
  URL:=$(PKG_SOURCE_URL)
  DEPENDS:= \
	+libpcap \
	+libpcre
  MAINTAINER:=Jiri Slachta <jiri@slachta.eu>
endef

define Package/$(PKG_NAME)/description
 Sipgrep is a powerful pcap-aware tool command line tool to sniff, 
 capture, display and troubleshoot SIP signaling over IP networks, 
 allowing the user to specify extended regular expressions matching 
 against SIP headers.
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/sipgrep $(1)/usr/bin/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
