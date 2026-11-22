# PonWrt 本地默认配置包：把必要的运行默认值固化进固件
include $(TOPDIR)/rules.mk

PKG_NAME:=ponwrt-defaults
PKG_VERSION:=1.1.0
PKG_RELEASE:=1

PKG_LICENSE:=GPL-2.0
PKG_MAINTAINER:=uioprr

include $(INCLUDE_DIR)/package.mk

define Package/ponwrt-defaults
  SECTION:=base
  CATEGORY:=Base system
  TITLE:=PonWrt default UCI/sysctl settings (flow offload, LAN IP, net tuning)
endef

PKGARCH:=all

define Package/ponwrt-defaults/description
  Ships uci-defaults that enable nftables flow offload (software + hardware),
  set LAN to 10.1.1.1/24, and apply kernel network tuning (buffers, conntrack,
  UDP timeouts) on first boot.
endef

define Build/Compile
endef

define Package/ponwrt-defaults/install
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./files/99-ponwrt-flowoffload $(1)/etc/uci-defaults/99-ponwrt-flowoffload
	$(INSTALL_BIN) ./files/99-ponwrt-lanip $(1)/etc/uci-defaults/99-ponwrt-lanip
	$(INSTALL_BIN) ./files/99-ponwrt-sysctl $(1)/etc/uci-defaults/99-ponwrt-sysctl
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) ./files/ponwrt-offload $(1)/usr/sbin/ponwrt-offload
endef

$(eval $(call BuildPackage,ponwrt-defaults))
