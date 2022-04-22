#
# Copyright (C) 2011-2020 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=upx
PKG_RELEASE:=1

PKG_MAINTAINER:=Xingwang Liao <kuoruan@gmail.com>
PKG_LICENSE:=GPL-2.0-only
PKG_LICENSE_FILES:=COPYING LICENSE

PKG_SOURCE_PROTO:=git
PKG_SOURCE_DATE:=2022-03-26
PKG_SOURCE_VERSION:=a54bef20057d72ab020df3812e90542bdcf56e1f
PKG_SOURCE_URL:=https://github.com/upx/upx.git
PKG_MIRROR_HASH:=d6d529791ab737f9c1cbc696073213a9690832967c28bf3092a6ef41a75c4460
PKG_SOURCE:=$(PKG_NAME)-$(PKG_SOURCE_DATE).tar.gz

include $(INCLUDE_DIR)/package.mk

define Package/upx
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=+libucl +libstdcpp +zlib
  TITLE:=The Ultimate Packer for eXecutables
  URL:=https://upx.github.io/
endef

define Package/upx/description
UPX is a free, portable, extendable, high-performance executable packer for
several different executable formats. It achieves an excellent compression ratio
and offers very fast decompression. Your executables suffer no memory overhead
or other drawbacks for most of the formats supported, because of in-place
decompression.
endef

MAKE_PATH := src

define Package/upx/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/upx.out $(1)/usr/bin/upx
endef

$(eval $(call BuildPackage,upx))
