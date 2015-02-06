#
# Copyright (c) 2014 Arduino LLC. All right reserved.
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=cpu-mcu-bridge
PKG_VERSION:=1.5.1-git
PKG_RELEASE:=3

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/8devices/YunBridge.git
PKG_SOURCE_VERSION:=fa2ec55a75c7bbfd09902a180218dc12e5a434aa
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

include $(INCLUDE_DIR)/package.mk

define Package/cpu-mcu-bridge
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=CPU-MCU Bridge
  DEPENDS:=+python-mini
endef

define Package/cpu-mcu-bridge/description
 Bridge lets linux and arduino communicate
endef

define Build/Compile
	# NOOP
endef

define Package/cpu-mcu-bridge/install
	$(INSTALL_DIR) $(1)/usr/lib/python2.7/bridge
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/bridge/*.py $(1)/usr/lib/python2.7/bridge

	$(INSTALL_DIR) $(1)/usr/lib/php/bridge
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/bridge/php/*.php $(1)/usr/lib/php/bridge
endef

$(eval $(call BuildPackage,cpu-mcu-bridge))
