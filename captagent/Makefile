#
# Copyright (C) 201& OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=captagent
PKG_VERSION:=6.2.11
PKG_RELEASE:=1
PKG_REV:=53967ebd9facfd59a2e0a7b949bf538638dd5da6
PKG_INSTALL:=1
PKG_FIXUP:=autoreconf libtool

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/sipcapture/captagent.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=$(PKG_REV)

PKG_BUILD_DIR=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/$(PKG_NAME)
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Telephony
  TITLE:=HEP Capture Agent for HOMER
  URL:=$(PKG_SOURCE_URL)
  DEPENDS:= \
	+libjson-c \
	+libpcap \
	+libpcre \
	+libexpat \
	+libuv
  MAINTAINER:=Jiri Slachta <jiri@slachta.eu>
endef

CONFIGURE_ARGS+=\
        --prefix=/usr/ \
        --exec-prefix=/usr/ \

define Package/$(PKG_NAME)/description
 aaa
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/captagent $(1)/usr/sbin/

	$(INSTALL_DIR) $(1)/usr/lib/captagent/modules
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/captagent/modules/*.so \
		$(1)/usr/lib/captagent/modules/

	$(INSTALL_DIR) $(1)/etc/captagent
	$(CP) $(PKG_INSTALL_DIR)/etc/captagent/* $(1)/etc/captagent

	$(INSTALL_DIR) $(1)/etc/captagent/captureplans
	$(CP) $(PKG_INSTALL_DIR)/etc/captagent/captureplans/* $(1)/etc/captagent/captureplans
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
