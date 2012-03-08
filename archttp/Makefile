PACKAGE_NAME = areca-archttp-binary
VERSION      = 1.87
ITERATION    = 1
ARCHITECTURE = amd64

CONTROL_FILE  = areca-archttp-binary.control
POSTINST_FILE = areca-archttp-binary.postinst
POSTRM_FILE   = areca-archttp-binary.postrm

CONFIG_FILE = /etc/areca/archttpsrv.conf

BUILD_HOME   = $(shell echo "${PWD}/package")
BUILD_PREFIX = /

FPM = $(shell which fpm)

package:
	$(FPM) -s dir -t deb -C $(BUILD_HOME) \
		--prefix $(BUILD_PREFIX) \
		--name $(PACKAGE_NAME) \
		--version $(VERSION) \
		--iteration $(ITERATION) \
		--architecture $(ARCHITECTURE) \
		--config-files $(CONFIG_FILE) \
		--post-install $(POSTINST_FILE) \
		--post-uninstall $(POSTRM_FILE) \
		--deb-custom-control $(CONTROL_FILE) 1> /dev/null

clean:
	rm -r -f *.deb

.PHONY: package
