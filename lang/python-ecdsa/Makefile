include $(TOPDIR)/rules.mk

PKG_NAME:=python-ecdsa
PKG_VERSION:=0.11
PKG_RELEASE:=1

PKG_SOURCE:=python-ecdsa-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://github.com/warner/python-ecdsa/archive
PKG_MD5SUM:=6a66d893053ec5c59804e82e2510b3b9
PKG_BUILD_DIR:=$(BUILD_DIR)/python-ecdsa-python-ecdsa-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-ecdsa
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=python-ecdsa
  URL:=https://github.com/warner/python-ecdsa
  DEPENDS:=+python
endef

define Package/ecdsa/description
   pure-python ECDSA signature/verification
endef

define Build/Compile
	$(call Build/Compile/PyMod,., \
		install --prefix="/usr" --root="$(PKG_INSTALL_DIR)" \
	)
endef

define Package/python-ecdsa/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-ecdsa))
