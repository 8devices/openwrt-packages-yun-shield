#
# Copyright (c) 2014 Arduino LLC. All right reserved.
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-arduino-webpanel
PKG_VERSION:=1.5.6
PKG_RELEASE:=3

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=http://arduino.cc/download.php?f=/
PKG_MD5SUM:=cda05d6c124a711927d1c5162608de61

include $(INCLUDE_DIR)/package.mk

define Package/luci-app-arduino-webpanel
  SECTION:=luci
  CATEGORY:=LuCI
  SUBMENU:=3. Applications
  TITLE:= simplified wifi configuration panel
  DEPENDS:=+luci +luci-lib-json +uhttpd-mod-lua +yun-scripts
endef

define Package/luci-app-arduino-webpanel/description
	simplified wifi configuration panel
endef

define Build/Compile
	# NOOP
endef

define Package/luci-app-arduino-webpanel/install
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/controller/arduino
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/view/arduino
	$(INSTALL_DIR) $(1)/www/luci-static/resources/arduino

	find $(PKG_BUILD_DIR)/usr/ -name '*.lua' -exec luac -s -o {} {} \;
	$(CP) $(PKG_BUILD_DIR)/usr/* $(1)/usr/
	$(CP) $(PKG_BUILD_DIR)/www/* $(1)/www/
endef

$(eval $(call BuildPackage,luci-app-arduino-webpanel))

