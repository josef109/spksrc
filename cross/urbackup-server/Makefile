PKG_NAME = urbackup-server
PKG_VERS = 2.5.37
PKG_EXT = tar.gz
PKG_DIST_NAME = $(PKG_NAME)-$(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://hndl.urbackup.org/Server/$(PKG_VERS)
PKG_DIST_FILE = $(PKG_NAME)-$(PKG_VERS).$(PKG_EXT)
PKG_DIR = $(PKG_NAME)-$(PKG_VERS)

DEPENDS = cross/curl cross/zlib cross/zstd cross/cryptopp cross/openssl
export BUILD_CURL_WITH="ldap"

HOMEPAGE = https://www.urbackup.org/
COMMENT  = UrBackup is an easy to setup open source client/server backup system, that through a combination of image and file backups accomplishes both data safety and a fast restoration time.
LICENSE  = AGPL-3.0

GNU_CONFIGURE = 1
CONFIGURE_ARGS = --enable-packaging #--with-mountvhd   #--enable-embedded-cryptopp -S-enable-embedded-zstd                       
CONFIGURE_ARGS += --with-zlib=$(STAGING_INSTALL_PREFIX)
CONFIGURE_ARGS += --with-crypto-prefix=$(STAGING_INSTALL_PREFIX)

ADDITIONAL_CXXFLAGS = -Os -pipe -fPIC
ADDITIONAL_CFLAGS = -Os

#ifeq ($(findstring $(ARCH),$(ARMv5_ARCHS) $(ARMv7L_ARCHS) $(ARMv7_ARCHS)),$(ARCH))
#ADDITIONAL_LDFLAGS = -static
#endif

include ../../mk/spksrc.cross-cc.mk
