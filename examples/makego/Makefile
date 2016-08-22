configure:
	curl https://glide.sh/get | sh
	glide install
	cd /tmp && rm -f -R semverbuild && git clone https://github.com/karamani/semverbuild && cp semverbuild/svbuild ~/bin/svbuild

update:
	glide up

compile:
	goimports -w ./*.go
	go tool vet ./*.go
	golint
	go test
	go install

build:
	echo $(NEW_VER); \
	if [ -z "$(NEW_VER)" ] ; then \
		echo "Не могу создать версию"; \
	else \
		go build -ldflags "-X main.Version=$(NEW_VER)" -o "bin/makego"; \
	fi

patch: export NEW_VER = `svbuild | tail -n 1`
patch: compile build

minor: export NEW_VER = `svbuild -l2 | tail -n 1`
minor: compile build

major: export NEW_VER = `svbuild -l1 | tail -n 1`
major: compile build