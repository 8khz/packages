#
# Copyright (C) 2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=captagent
PKG_VERSION:=6.1.0.20
PKG_RELEASE:=1
PKG_REV:=bfc0179e769f61cd80cc9516d34f61c979f02b6d
PKG_INSTALL:=1
PKG_FIXUP:=autoreconf libtool

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/sipcapture/captagent.git
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
  TITLE:=HEP Capture Agent for HOMER
  URL:=$(PKG_SOURCE_URL)
  DEPENDS:= \
	+libpcap \
	+libpcre \
	+libexpat \
	+libuv \
	@BROKEN
  MAINTAINER:=Jiri Slachta <jiri@slachta.eu>
endef

CONFIGURE_ARGS+=\
        --prefix=/usr/ \
        --exec-prefix=/usr/ \

define Package/$(PKG_NAME)/description
 aaa
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/bin
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
