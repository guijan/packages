#
# Copyright (C) 2022 Guilherme Janczak <guilherme.janczak@yandex.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=dictpw
PKG_VERSION:=1.2.0
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://github.com/guijan/dictpw/releases/download/v$(PKG_VERSION)/
PKG_HASH:=8f49df1979981ea7a827efbd94104443a404301c0521e613809d44cb15838d0a

PKG_MAINTAINER:=Guilherme Janczak <guilherme.janczak@yandex.com>
PKG_LICENSE:=ISC
PKG_LICENSE_FILES:=LICENSE.md

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/meson.mk

define Package/dictpw
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Generate password from dictionary
  URL:=https://github.com/guijan/dictpw/
  DEPENDS:=+libobsd
endef

define Package/dictpw/description
  Dictpw randomly picks 5 words off a 7776-word dictionary and prints them with 
  a dot between each word. This is the Diceware method of password generation
  from the command line.
endef

define Package/dictpw/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/dictpw $(1)/usr/bin/
endef

$(eval $(call BuildPackage,dictpw))
