## OSX - Tested on EI CAPITAN
Install Mac Ports
```
sudo port install git gsed gawk binutils gperf grep gettext py-serial wget libtool autoconf automake
```

```
hdiutil create -size 5g -fs "Case-sensitive HFS+" -volname ESPTools ESPTools.sparsebundle
hdiutil attach ESPTools.sparsebundle
sudo ln -s /Volumes/ESPTools/ /tools
mkdir /tools/esp8266 /tools/esp8266/sdk /tools/esp8266/compiler
cd /tools/esp8266/compiler

git clone -b lx106 git://github.com/jcmvbkbc/crosstool-NG.git 
cd crosstool-NG
sed -i.bak '1s/^/gettext=\'$'\n/' crosstool-NG/kconfig/Makefile
./bootstrap && ./configure --prefix=`pwd` && make && make install
./ct-ng xtensa-lx106-elf
./ct-ng build

```

If have nay error like `error: unknown type name 'ptrdiff_t'` please exec command  `sed -i.bak '/__need_size_t/d' .build/src/gmp-5.1.3/gmp-h.in`, then `./ct-ng build again`  (look at: https://github.com/pfalcon/esp-open-sdk/issues/45)
`nano ~/.bash_profile`

add this line:
`export PATH=$PATH:/tools/esp8266/compiler/crosstool-NG/builds/xtensa-lx106-elf/bin`
Update ENV variable
`source ~/.bash_profile`
Test: `xtensa-lx106-elf-gcc -v`

Install esptool.py 
```
cd /tools/esp8266
git clone https://github.com/themadinventor/esptool.git
```

Download lastest SDK from ... to /tools/esp8266/sdk/
Download libc, libhal, include file
```
cd /tools/esp8266/compiler/crosstool-NG/builds/xtensa-lx106-elf/xtensa-lx106-elf/sysroot/usr
wget -O lib/libc.a https://github.com/esp8266/esp8266-wiki/raw/master/libs/libc.a
wget -O lib/libhal.a https://github.com/esp8266/esp8266-wiki/raw/master/libs/libhal.a
wget -O include.tgz https://github.com/esp8266/esp8266-wiki/raw/master/include.tgz
tar -xvzf include.tgz

```
Build test:
```
cd /tools/esp8266
mkdir projects
cd projects
git clone https://github.com/tuanpmt/esp_mqtt
cd esp_mqtt
make
```

## Windows - tested on Windows 8.1

### Install SDK and tools
- Download Unofficial Development kit for Windows from: http://programs74.ru/udkew-en.html, only need xtensa-lx106-elf compiler and utils sections. It will install at C:/Espressif folder, utils at: C:\MinGW 
- Add C:\MinGW\msys\1.0\bin, C:\MinGW\bin to ENV PATH 
- Download lastest sdk from: bbs.espressif.com to c:/Espressif/sdk folder 