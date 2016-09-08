configure:
	cd /tmp && rm -f -R semverbuild && git clone https://github.com/karamani/semverbuild && cp semverbuild/svbuild $$GOPATH/bin/svbuild

build:
	$(eval newver := $(shell (svbuild -$(VER_LVL) | tail -n 1)))

	if [ -z "$(newver)" ] ; then \
		echo "Fatal: it's impossible to create new version"; \
	else \
		go build -ldflags "-X main.Version=$(newver)" -o "bin/makego"; \
	fi

patch: export VER_LVL = l3
patch: build

minor: export VER_LVL = l2
minor: build

major: export VER_LVL = l1
major: build
