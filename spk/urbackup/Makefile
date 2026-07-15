SPK_NAME = urbackup
SPK_VERS = 2.5.37
SPK_REV = 5
SPK_ICON = src/urbackup.png
DSM_UI_DIR = app

DEPENDS = cross/urbackup-server

# see cross/cryptopp
UNSUPPORTED_ARCHS = $(PPC_ARCHS)

MAINTAINER = josef109
DESCRIPTION = UrBackup is an easy to setup Open Source client/server backup system, that through a combination of image and file backups accomplishes both data safety and a fast restoration time.
RELOAD_UI = yes
DISPLAY_NAME = UrBackup
CHANGELOG = "Initial package release with server and client"

HOMEPAGE = https://www.urbackup.org/
LICENSE  = AGPL-3.0


# 'auto' reserved value grabs SPK_NAME 
SERVICE_USER         = auto
GROUP=sc-backup

SERVICE_SETUP        = src/service-setup.sh
STARTABLE            = yes

SERVICE_PORT = 55414
ADMIN_PORT = $(SERVICE_PORT)
SERVICE_PORT_TITLE =  Urbackup (HTTP)

POST_STRIP_TARGET = urbackup_extra_install

.PHONY: urbackup_extra_install
urbackup_extra_install:
	install -m 755 -d $(STAGING_DIR)/bin
	install -m 755 src/helper_fix $(STAGING_DIR)/bin

SPK_COMMANDS = bin/blockalign bin/urbackupclientctl sbin/urbackupclientbackend

include ../../mk/spksrc.spk.mk
