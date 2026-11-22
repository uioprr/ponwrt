# PonWrt 本地默认配置包：把必要的运行默认值固化进固件
include $(TOPDIR)/rules.mk

PKG_NAME:=ponwrt-defaults
PKG_VERSION:=1.0.0
PKG_RELEASE:=1

PKG_LICENSE:=GPL-2.0
PKG_MAINTAINER:=uioprr

include $(INCLUDE_DIR)/package.mk

define Package/ponwrt-defaults
  SECTION:=base
  CATEGORY:=Base system
  TITLE:=PonWrt default UCI settings (flow offload, LAN IP)
endef

PKGARCH:=all

define Package/ponwrt-defaults/description
  Ships uci-defaults that enable nftables flow offload (software + hardware)
  on first boot, so PPPoE/LAN forwarding lands on the PPE engine instead of
  the CPU.
endef

define Build/Compile
endef

define Package/ponwrt-defaults/install
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./files/99-ponwrt-flowoffload $(1)/etc/uci-defaults/99-ponwrt-flowoffload
	$(INSTALL_BIN) ./files/99-ponwrt-lanip $(1)/etc/uci-defaults/99-ponwrt-lanip
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) ./files/ponwrt-offload $(1)/usr/sbin/ponwrt-offload
endef

$(eval $(call BuildPackage,ponwrt-defaults))
