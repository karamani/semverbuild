# Install
## Ubuntu
```
$ cd /tmp && rm -f -R semverbuild && git clone https://github.com/karamani/semverbuild && cp semverbuild/svbuild ~/bin/svbuild
```

# Examples
```
svbuild -l1 # autoincrement major version

svbuild -l2 # autoincrement minor version

svbuild -l3 # autoincrement path

svbuild # autoincrement path
```
