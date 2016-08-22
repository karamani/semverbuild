# Install
## Ubuntu
```
$ cd /tmp && rm -f -R semverbuild && git clone https://github.com/karamani/semverbuild && cp semverbuild/svbuild ~/bin/svbuild
```

# Examples
```
gobuild -l1 # autoincrement major version

gobuild -l2 # autoincrement minor version

gobuild -l3 # autoincrement path

gobuild # autoincrement path
```
