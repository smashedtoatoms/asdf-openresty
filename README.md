# asdf-openresty

OpenResty plugin for [asdf](https://github.com/asdf-vm/asdf) version manager

## Dependencies
_This requires [brew](http://brew.sh) if you're on a mac, or a debian flavored linux.  If you need it to work on something else, you'll likely need to modify the plugin._  

1. You will need a compiler.
  * Mac
    1. ```gcc```
    1. Hit the ok button and it will install.  If it already has it, then you are good.
  * Ubuntu  
    1. ```sudo apt-get install linux-headers-$(uname -r) build-essential```
1. You will need openssl
  * Mac 
    1. ```brew install openssl``` 
  * Ubuntu 
    1. ```sudo apt-get install openssl libssl-dev```
1. You will need pcre 
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
