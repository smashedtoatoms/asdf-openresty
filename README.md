# asdf-openresty ![Build](https://github.com/smashedtoatoms/asdf-openresty/workflows/Build/badge.svg?branch=master)

OpenResty plugin for [asdf](https://github.com/asdf-vm/asdf) version manager

## Dependencies
_This requires [brew](http://brew.sh) if you're on a mac, or a debian flavored linux.  If you need it to work on something else, you'll likely need to modify the plugin._

1. You will need a compiler.
  * Mac
    1. ```gcc```
    1. Hit the ok button and it will install.  If it already has it, then you are good.
  * Ubuntu
    1. ```sudo apt-get install linux-headers-$(uname -r) build-essential```
2. You will need openssl
  * Mac
    1. ```brew install openssl```
  * Ubuntu
    1. ```sudo apt-get install openssl libssl-dev```
3. You will need pcre
  * Mac
    1. ```brew install pcre```
  * Ubuntu
    1. ```sudo apt-get install libpcre3 libpcre3-dev```

## Install
```
asdf plugin-add openresty https://github.com/smashedtoatoms/asdf-openresty.git
```

## Use

Check [asdf](https://github.com/asdf-vm/asdf) readme for instructions on how to install & manage versions of OpenResty.

When installing OpenResty using `asdf install`, you can pass custom configure options with the following env vars:

* `OPENRESTY_CONFIGURE_OPTIONS` - use only your configure options
* `OPENRESTY_EXTRA_CONFIGURE_OPTIONS` - append these configure options along with ones that this plugin already uses

If you are using arch based distribution, you might need to manually specify openssl version:
```
OPENRESTY_EXTRA_CONFIGURE_OPTIONS="--with-cc-opt=-I/usr/include/openssl-1.0 --with-ld-opt=-L/usr/lib/openssl-1.0" asdf install openresty 1.11.2.2
```

If the above method still doesn't works, try using [older version of openssl on their website](https://www.openssl.org/source/old/1.0.1/).
```
# Download openssl
curl -O https://www.openssl.org/source/old/1.0.1/openssl-1.0.1u.tar.gz
tar xzf openssl-1.0.1u.tar.gz
./configure --with-openssl=openssl-1.0.1u
# Use downloaded openssl to build openresty
OPENRESTY_EXTRA_CONFIGURE_OPTIONS=--with-openssl=PATH_TO_DOWNLOADED_FILE/openssl-1.0.1u asdf install openresty 1.11.2.2
```
