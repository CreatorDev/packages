#
# Copyright (C) 2006-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=gst1-rtsp-server
PKG_VERSION:=1.8.2
PKG_RELEASE:=1

PKG_LICENSE:=LGPLv2+
PKG_LICENSE_FILES:=COPYING COPYING.LIB

PKG_BUILD_DIR:=$(BUILD_DIR)/gst-rtsp-server-$(PKG_VERSION)
PKG_SOURCE:=gst-rtsp-server-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=http://gstreamer.freedesktop.org/src/gst-rtsp-server
PKG_MD5SUM:=193ae75a676f39294f64b162bbe2369d

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

PKG_BUILD_DEPENDS:= libgstreamer1 gstreamer1-plugins-base

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/gst1-rtsp-server
  SECTION:=multimedia
  CATEGORY:=Multimedia
  TITLE:=GStreamer based RTSP server
  URL:=http://gstreamer.freedesktop.org/modules/gst-rtsp-server.html
  DEPENDS:= +libgstreamer1 +gstreamer1-plugins-base +libgst1app \
	    +libgst1net +libgst1rtp +libgst1rtsp +libgst1sdp
endef

define Package/gst1-rtsp-server/description
  GStreamer based RTSP server
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/
	( cd $(PKG_INSTALL_DIR); $(CP) \
		./usr/include/* \
		$(1)/usr/include/ \
	)
	$(INSTALL_DIR) $(1)/usr/lib/
	( cd $(PKG_INSTALL_DIR); $(CP) \
		./usr/lib/libgst*.{la,so} \
		$(1)/usr/lib/ \
	)
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	( cd $(PKG_INSTALL_DIR); $(CP) \
		./usr/lib/pkgconfig/gstreamer*.pc \
		$(1)/usr/lib/pkgconfig/ \
	)
endef

define Package/gst1-rtsp-server/install
	$(INSTALL_DIR) $(1)/usr/include/
	( cd $(PKG_INSTALL_DIR); $(CP) \
		./usr/include/* \
		$(1)/usr/include/ \
	)
	$(INSTALL_DIR) $(1)/usr/lib/
	( cd $(PKG_INSTALL_DIR); $(CP) \
		./usr/lib/libgst*.so* \
		$(1)/usr/lib/ \
	)
endef

$(eval $(call BuildPackage,gst1-rtsp-server))
