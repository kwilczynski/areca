PACKAGE_NAME = areca-cli-binary
VERSION      = 1.86
ITERATION    = 1
ARCHITECTURE = amd64

CONTROL_FILE  = areca-cli-binary.control
POSTINST_FILE = areca-cli-binary.postinst
POSTRM_FILE   = areca-cli-binary.postrm

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
		--post-install $(POSTINST_FILE) \
		--post-uninstall $(POSTRM_FILE) \
		--deb-custom-control $(CONTROL_FILE) 1> /dev/null

clean:
	rm -r -f *.deb

.PHONY: package
