

	
  1. Chip ESP8266


ESP8266 là chip của ESPRESSIF có tích hợp WIFI networking solution. Ngoài ra chip này còn hỗ trợ các ngoại vi khác như GPIO, serial port, SPI, TWI ... Tóm lại, ESP8266 là một chip gía rẻ phù hợp cho các hobby widget IoT hiện tại.

Các thông tin khác về ESP8266 có thể xem thêm tại [Official Website Espresif](http://espressif.com/en/products/esp8266/)



	
  2. Các module dùng ESP8266


Tuy nhiên, để đưa chip đến với các end user thì phải kể đến các module rất tiện dụng được thiết kế dựa trên ESP8266. Có rất nhiều các phiên bản module khác nhau từ ESP-01 đến ESP-13. Và thêm vào đó các module này có gía rất bèo. Chỉ khoảng dưới 125k, thậm chí có cửa hàng còn đề gía có 90k (<4.5$). Nguồn Google :D.

![esp_modules_front](https://vnarmyblog.files.wordpress.com/2016/10/esp_modules_front.jpg)

![esp_modules_back](https://vnarmyblog.files.wordpress.com/2016/10/esp_modules_back.jpg)


## Summary Table








<table class="inline" >

<tr class="row0" >
Board ID
pins
pitch
form factor
LEDs
Antenna
Ant.Socket
Shielded
dimensions mm
</tr>

<tbody >
<tr class="row1" >

<td class="col0" >ESP-01
</td>

<td class="col1" >8
</td>

<td class="col2" >.1“
</td>

<td class="col3" >2×4 DIL
</td>

<td class="col4" >Yes
</td>

<td class="col5" >Etched-on PCB
</td>

<td class="col6" >No
</td>

<td class="col7" >No
</td>

<td class="col8" >14.3 x 24.8
</td>
</tr>
<tr class="row2" >

<td class="col0" >ESP-02
</td>

<td class="col1" >8
</td>

<td class="col2" >.1”
</td>

<td class="col3" >2×4 notch
</td>

<td class="col4" >No?
</td>

<td class="col5" >None
</td>

<td class="col6" >Yes
</td>

<td class="col7" >No
</td>

<td class="col8" >14.2 x 14.2
</td>
</tr>
<tr class="row3" >

<td class="col0" >ESP-03
</td>

<td class="col1" >14
</td>

<td class="col2" >2mm
</td>

<td class="col3" >2×7 notch
</td>

<td class="col4" >No
</td>

<td class="col5" >Ceramic
</td>

<td class="col6" >No
</td>

<td class="col7" >No
</td>

<td class="col8" >17.3 x 12.1
</td>
</tr>
<tr class="row4" >

<td class="col0" >ESP-04
</td>

<td class="col1" >14
</td>

<td class="col2" >2mm
</td>

<td class="col3" >2×4 notch
</td>

<td class="col4" >No?
</td>

<td class="col5" >None
</td>

<td class="col6" >No
</td>

<td class="col7" >No
</td>

<td class="col8" >14.7 x 12.1
</td>
</tr>
<tr class="row5" >

<td class="col0" >ESP-05
</td>

<td class="col1" >5
</td>

<td class="col2" >.1“
</td>

<td class="col3" >1×5 SIL
</td>

<td class="col4" >No
</td>

<td class="col5" >None
</td>

<td class="col6" >Yes
</td>

<td class="col7" >No
</td>

<td class="col8" >14.2 x 14.2
</td>
</tr>
<tr class="row6" >

<td class="col0" >ESP-06
</td>

<td class="col1" >12+GND
</td>

<td class="col2" >misc
</td>

<td class="col3" >4×3 dice
</td>

<td class="col4" >No
</td>

<td class="col5" >None
</td>

<td class="col6" >No
</td>

<td class="col7" >Yes
</td>

<td class="col8" >?
</td>
</tr>
<tr class="row7" >

<td class="col0" >ESP-07
</td>

<td class="col1" >16
</td>

<td class="col2" >2mm
</td>

<td class="col3" >2×8 pinhole
</td>

<td class="col4" >Yes
</td>

<td class="col5" >Ceramic
</td>

<td class="col6" >Yes
</td>

<td class="col7" >Yes
</td>

<td class="col8" >20.0 x 16.0
</td>
</tr>
<tr class="row8" >

<td class="col0" >ESP-08
</td>

<td class="col1" >14
</td>

<td class="col2" >2mm
</td>

<td class="col3" >2×7 notch
</td>

<td class="col4" >No
</td>

<td class="col5" >None
</td>

<td class="col6" >No
</td>

<td class="col7" >Yes
</td>

<td class="col8" >17.0 x 16.0
</td>
</tr>
<tr class="row9" >

<td class="col0" >ESP-09
</td>

<td class="col1" >12+GND
</td>

<td class="col2" >misc
</td>

<td class="col3" >4×3 dice
</td>

<td class="col4" >No
</td>

<td class="col5" >None
</td>

<td class="col6" >No
</td>

<td class="col7" >No
</td>

<td class="col8" >10.0 x 10.0
</td>
</tr>
<tr class="row10" >

<td class="col0" >ESP-10
</td>

<td class="col1" >5
</td>

<td class="col2" >2mmm?
</td>

<td class="col3" >1×5 notch
</td>

<td class="col4" >No
</td>

<td class="col5" >None
</td>

<td class="col6" >No
</td>

<td class="col7" >No
</td>

<td class="col8" >14.2 x 10.0
</td>
</tr>
<tr class="row11" >

<td class="col0" >ESP-11
</td>

<td class="col1" >8
</td>

<td class="col2" >1.27mm
</td>

<td class="col3" >1×8 pinhole
</td>

<td class="col4" >No?
</td>

<td class="col5" >Ceramic
</td>

<td class="col6" >No
</td>

<td class="col7" >No
</td>

<td class="col8" >17.3 x 12.1
</td>
</tr>
<tr class="row12" >

<td class="col0" >ESP-12
</td>

<td class="col1" >16
</td>

<td class="col2" >2mm
</td>

<td class="col3" >2×8 notch
</td>

<td class="col4" >Yes
</td>

<td class="col5 rightalign" >Etched-on PCB
</td>

<td class="col6" >No
</td>

<td class="col7" >Yes
</td>

<td class="col8" >24.0 x 16.0
</td>
</tr>
<tr class="row13" >

<td class="col0" >ESP-12-E
</td>

<td class="col1" >22
</td>

<td class="col2" >2mm
</td>

<td class="col3" >2×8 notch
</td>

<td class="col4" >Yes
</td>

<td class="col5 rightalign" >Etched-on PCB
</td>

<td class="col6" >No
</td>

<td class="col7" >Yes
</td>

<td class="col8" >24.0 x 16.0
</td>
</tr>
<tr class="row14" >

<td class="col0" >ESP-13
</td>

<td class="col1" >18
</td>

<td class="col2" >1.5mm
</td>

<td class="col3" >2×9
</td>

<td class="col4" >?
</td>

<td class="col5 rightalign" >Etched-on PCB
</td>

<td class="col6" >No
</td>

<td class="col7" >Yes
</td>

<td class="col8" >? x ?
</td>
</tr>
<tr class="row15" >

<td class="col0" >WROOM-02
</td>

<td class="col1" >18
</td>

<td class="col2" >1.5mm
</td>

<td class="col3" >2×9
</td>

<td class="col4" >No
</td>

<td class="col5" >Etched on PCB
</td>

<td class="col6" >No
</td>

<td class="col7" >Yes
</td>

<td class="col8" >20.0 x 18.0
</td>
</tr>
<tr class="row16" >

<td class="col0" >WT8266-S1
</td>

<td class="col1" >18
</td>

<td class="col2" >1.5mm
</td>

<td class="col3" >3×6
</td>

<td class="col4" >1
</td>

<td class="col5" >Etched on PCB
</td>

<td class="col6" >No
</td>

<td class="col7" >Yes
</td>

<td class="col8" >15.0 x 18.6
</td>
</tr>
</tbody>
</table>






_[(Nguồn esp8266.com)](http://www.esp8266.com/wiki/doku.php?id=esp8266-module-family#modules_family)_



	
  3. Build Toolchain.


Lan man vậy đủ rồi. Bây giờ là phần chính tôi muốn nói trong post này. Đó là xây dựng bộ công cụ để làm việc với ESP8266.

Các module ESP đều được ship kèm với bộ firmware chuẩn hỗ trợ tập lệnh AT. Ngoài ra, để tận dụng các tính năng đi kèm, chúng ta còn có thể build một bản firmware riêng. Việc này được thực hiện thông qua bộ toolchain của Espressif. Do vậy, bước 1 sẽ là cài đặt bộ toolchain đó. Ở đây tôi thực hiện việc cài đặt trên Ubuntu 14.04 32-bit:

    
    #Install needed dependencies
    apt-get install git autoconf build-essential gperf bison flex texinfo libtool libncurses5-dev wget gawk libc6-dev-i386 python-serial libexpat-dev
    mkdir /opt/Espressif
    chown $username /opt/Espressif/
    
    # Install the Xtensa crosstool-NG
    cd /opt/Espressif
    git clone -b lx106 git://github.com/jcmvbkbc/crosstool-NG.git
    cd crosstool-NG
    ./bootstrap && ./configure --prefix=`pwd` && make && make install
    ./ct-ng xtensa-lx106-elf
    ./ct-ng build
    PATH=$PWD/builds/xtensa-lx106-elf/bin:$PATH
    echo 'PATH=/opt/Espressif/crosstool-NG/builds/xtensa-lx106-elf/bin:$PATH' >> ~/.profile
    sudo cp ct-ng.comp /etc/bash_completion.d/
    
    # Setting up the Espressif SDK
    cd /opt/Espressif
    mkdir ESP8266_SDK
    wget -O esp_iot_sdk_v1.1.1_15_06_05.zip https://github.com/esp8266/esp8266-wiki/raw/master/sdk/esp_iot_sdk_v1.1.1_15_06_05.zip
    unzip esp_iot_sdk_v1.1.1_15_06_05.zip
    mv esp_iot_sdk_v1.1.1/* ESP8266_SDK
    mv License ESP8266_SDK/
    mv release_note.txt ESP8266_SDK/
    rm -rf esp_iot_sdk_v1.1.1
    rm *.zip
    
    # Patching
    cd /opt/Espressif/ESP8266_SDK
    sed -i -e 's/xt-ar/xtensa-lx106-elf-ar/' -e 's/xt-xcc/xtensa-lx106-elf-gcc/' -e 's/xt-objcopy/xtensa-lx106-elf-objcopy/' Makefile
    mv examples/IoT_Demo .
    
    # Installing Xtensa libraries and headers
    cd /opt/Espressif/ESP8266_SDK
    wget -O lib/libc.a https://github.com/esp8266/esp8266-wiki/raw/master/libs/libc.a
    wget -O lib/libhal.a https://github.com/esp8266/esp8266-wiki/raw/master/libs/libhal.a
    wget -O include.tgz https://github.com/esp8266/esp8266-wiki/raw/master/include.tgz
    tar -xvzf include.tgz
    rm include.tgz
    
    # Installing the ESP image tool
    cd /opt/Espressif
    wget -O esptool_0.0.2-1_i386.deb https://github.com/esp8266/esp8266-wiki/raw/master/deb/esptool_0.0.2-1_i386.deb
    sudo dpkg -i esptool_0.0.2-1_i386.deb
    
    # Installing the ESP upload tool
    cd /opt/Espressif
    git clone https://github.com/themadinventor/esptool esptool-py
    sudo ln -s $PWD/esptool-py/esptool.py crosstool-NG/builds/xtensa-lx106-elf/bin/


Tham khảo thêm tại:

[https://github.com/esp8266/esp8266-wiki/wiki/Toolchain](https://github.com/esp8266/esp8266-wiki/wiki/Toolchain)

Giải thích sơ sơ chút là trong toolchain cài đặt ở trên có cài 1 bộ ESP upload tool viết trên Python. Tuy nhiên, tôi không tài nào upload được với tool này. Do vậy tôi có dùng 1 tool khác để upload sẽ được giới thiệu ở phần dưới.



	
  4. Blinky the ESP


Ok. Như vậy bước đầu đã xong bộ tool làm việc. Git phần sample về và test thử thôi.

    
    cd /opt/Espressif
    git clone https://github.com/esp8266/source-code-examples.git
    cd source-code-examples/blinky
    make


Sau khi make sẽ tạo thư mục firmware gồm 2 file 0x00000.bin và 0x40000.bin. Nạp cho module thôi.

![](https://importhack.files.wordpress.com/2014/11/esp8266-reflash-firmware.png)

Nối module và USB2COM như trên. Để dành quyền truy nhập USB2COM cần thực hiện:

    
    sudo adduser $username dialout


Sau đó nạp firmware cho module:

    
    cd /opt/Espressif/source-code-examples/blinky
    make ESPPORT=/dev/ttyUSB0 flash


Nối oscilloscope hay LED vào chân GPIO2 để quan sát tín hiệu.

Trong trường hợp nạp firmware không được có thể tải tool khác là [ESP8266flasher](https://github.com/nodemcu/nodemcu-flasher). Chạy rất ổn định.



	
  5. Resource on the net


Official: http://espressif.com/en/products/esp8266/

Forum: http://esp8266.com

Other projects: https://hackaday.io

And Google.com

