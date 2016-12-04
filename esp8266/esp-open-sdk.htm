~~~~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset='utf-8'>
</head>
<body>
Hiện tại cộng đồng ESP đang chuyển qua dùng <a href="https://github.com/pfalcon/esp-open-sdk">esp-open-sdk</a> bởi vì phiên bản này dễ dàng cài đặt và update cũng như nó sử dụng các tool của open source, đặc biệt là bao gồm cả the superior libc. Do vậy ở đây tôi sẽ nói về việc cài đặt esp-open-sdk.
<h2><strong>Cài đặt</strong></h2>
<pre class="theme:solarized-dark lang:default decode:true">#Install needed dependencies
sudo apt-get -y install git autoconf build-essential
sudo apt-get -y install gperf bison flex texinfo libtool libncurses5-dev wget gawk libc6-dev python-serial libexpat-dev dpkg-dev unzip

# Install the esp-open-sdk toolchain
cd /opt/Espresif/
sudo git clone https://github.com/pfalcon/esp-open-sdk.git
sudo chown -R $username esp-open-sdk
cd esp-open-sdk
make STANDALONE=y
echo 'PATH=$PATH:/opt/Espresif/esp-open-sdk/xtensa-lx106-elf/bin' >> ~/.profile
echo 'PATH=$PATH:/opt/Espresif/esp-open-sdk/esptool' >> ~/.profile
PATH=$PATH:/opt/Espresif/esp-open-sdk/xtensa-lx106-elf/bin
PATH=$PATH:/opt/Espresif/esp-open-sdk/esptool

# Installing the ESP image tool
cd /opt/Espresif/esp-open-sdk
wget -O esptool_0.0.2-1_i386.deb https://github.com/esp8266/esp8266-wiki/raw/master/deb/esptool_0.0.2-1_i386.deb
sudo dpkg -i esptool_0.0.2-1_i386.deb
rm esptool_0.0.2-1_i386.deb</pre>
Việc cài đặt có lẽ sẽ mất khoảng hơn 1 tiếng. Chú ý việc thay $username bằng user tương ứng.

Nếu muốn thay đổi phiên bản cài đặt thì khi trước make cần thay đổi phiên bản trong Makefile (dòng 3). Xem thêm tại: http://www.esp8266.com/wiki/doku.php?id=toolchain
<h2><strong>Update</strong></h2>
Việc update thực hiện đơn giản với vài dòng lệnh:
<pre class="theme:solarized-dark lang:default decode:true ">cd /opt/Espressif/esp-open-sdk
make clean
git pull
git submodule update</pre>
Trong các tài liệu trên net thì đều nói nếu không chạy make clean thì sẽ gây ra các lỗi khi build lại phiên bản. Tuy nhiên trong lần cài đặt đầu tiên tôi sẽ không chạy make clean do nó sẽ xóa các phần vừa cài đặt.
<h2>Basic Example.</h2>
Ok, bây giờ là lúc test thử với basic_example trong thư mục source_code_example (xem lại <a href="http://chungcu-hanoi.net/ehoaviet.com/2015/10/24/getting-started-with-esp8266/">getting-started-with-esp8266</a>). Tuy nhiên, trước tiên cần phải patch lại Makefile (hoặc edit lại) để chuyển qua dùng open sdk.

Mở file user_config.h trong thư mục user. Sửa lại 2 dòng config trong đó để phù hợp với Access Point.
<pre class="theme:terminal lang:default decode:true">cd /opt/Espressif/source-code-examples/basic_example
sed -i 's/crosstool-NG\/builds\/xtensa-lx106-elf\/bin/esp-open-sdk\/xtensa-lx106-elf\/bin/g' Makefile
sed -i 's/ESP8266_SDK/esp-open-sdk\/sdk/g' Makefile
make</pre>
Nạp 2 file 0x00000 và 0x40000.

Vào AP để kiểm tra trong DHCP Client List xem ESP đã kết nối được chưa. Hoặc nối với cổng RS232 để xem kết nối.

Để chuyển ESP thành AP thì cũng sửa file user_config.h. Đây chính SSID và Password của ESP khi kết nối đến.

Sửa hàm user_init trong file user_main.c
<pre class="lang:default decode:true ">void ICACHE_FLASH_ATTR
user_init()
{
char ssid[32] = SSID;
char password[64] = SSID_PASSWORD;

//struct station_config stationConf;
struct softap_config apConfig;

// Set baud rate of debug port
uart_div_modify(0,UART_CLK_FREQ / 9600);

//Set station mode
wifi_set_opmode( 0x2 );

//Set ap settings
//os_memcpy(&stationConf.ssid, ssid, 32);
//os_memcpy(&stationConf.password, password, 64);
// wifi_station_set_config(&stationConf);

os_memcpy(&apConfig.ssid, ssid, 32);
os_memcpy(&apConfig.password, password, 64);

apConfig.authmode = AUTH_WPA_PSK;
apConfig.channel = 7;
apConfig.max_connection = 255; // 1?
apConfig.ssid_hidden = 0;

wifi_softap_set_config(&apConfig);
//Start os task
system_os_task(loop, user_procTaskPrio,user_procTaskQueue, user_procTaskQueueLen);

system_os_post(user_procTaskPrio, 0, 0 );
}</pre>
Build và nạp cho ESP.
</body>
</html>
~~~~~~
