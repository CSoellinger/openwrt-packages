# Fastfetch Makefile for OpenWRT
#
# Lizenz: MIT
# Autor: Christopher Söllinger

include $(TOPDIR)/rules.mk

PKG_NAME:=fastfetch
PKG_VERSION:=2.23.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/fastfetch-cli/fastfetch/fastfetch.git
PKG_SOURCE_VERSION:=v$(PKG_VERSION)

PKG_MAINTAINER:=Christopher Söllinger <zerogiven@gmail.com>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk

define Package/fastfetch
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Fastfetch - a fast system information tool
  URL:=https://github.com/LinusDierheimer/fastfetch
endef

define Package/fastfetch/description
  Fastfetch is a fast and feature-rich system information tool, similar to neofetch.
endef

define Build/Prepare
  $(call Build/Prepare/Default)
endef

define Build/Configure
  $(call Build/Configure/Default)
endef

define Build/Compile
  $(MAKE) -C $(PKG_BUILD_DIR)
endef

define Package/fastfetch/install
  $(INSTALL_DIR) $(1)/usr/bin
  $(INSTALL_BIN) $(PKG_BUILD_DIR)/fastfetch $(1)/usr/bin/
endef

$(eval $(call BuildPackage,fastfetch))
