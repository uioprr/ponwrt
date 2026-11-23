# This is free software, licensed under the Apache License, Version 2.0 .

include $(TOPDIR)/rules.mk

PKG_VERSION:=1.2.1
PKG_RELEASE:=1

PKG_LICENSE:=Apache-2.0
PKG_LICENSE_FILES:=LICENSE

LUCI_TITLE:=LuCI Airoha SoC Status (NPU, CPU, Frame Engine)
LUCI_MAINTAINER:=luanmuc
LUCI_URL:=https://github.com/luanmuc/luci-app-airoha-npu
LUCI_DESCRIPTION:=Status page for Airoha EN7581 and AN7583 SoCs: NPU state, Frame \
	Engine ports/PSE queues, PPE flow offload table, CPU frequency, independent \
	temperature sensors and PLL fallback frequency. Chinese localization included.
LUCI_DEPENDS:=+luci-base @TARGET_airoha

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
