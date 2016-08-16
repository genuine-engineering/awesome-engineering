# ROADMAP phát triển nền tảng IoT cộng đồng
## Lời nói đầu:

## Tổng quan hệ thống IoT 

### Thiết bị phần cứng End device 

Mục tiêu việc phát triển các nền tảng End Device để hỗ trợ sản xuất hàng loạt và hoạt động một cách ổn định, chuyên nghiệp. 
Ngay từ đầu, các nhà phát triển có thể thao tác trên các core này một cách dễ dàng. Khi ứng dụng có khả năng triển khai thực tế, có thể phát triển những core prototype này thành sản phẩm hoàn thiện.

- WIFI - dự án wifi-iot-core (ESP8266 kết hợp STM32 giá rẻ, bổ sung khuyết điểm thiếu USB, thiếu Analog và IO cho ESP8266)
    + [wifi-iot-core-hw](https://github.com/genuine-engineering/wifi-iot-core-stm32-hw) phần cứng vẽ bằng kicad 
    + [wifi-iot-core-stm32-fw](https://github.com/genuine-engineering/wifi-iot-core-stm32-fw) firmware cho STM32, hỗ trợ CDC và auto detect sync frame, tự động chuyển ESP8255 sang chế độ nạp khi nhận sync frame từ esptool.py, hỗ trợ giao thức SLIP nhận lệnh thực thi từ ESP8266, trao đổi dữ liệu với PC ...
    + [wifi-iot-core-esp8266-fw](https://github.com/genuine-engineering/wifi-iot-core-esp8266-fw) firmware C base trên official SDK của Espressif, đảm bảo ổn định và dễ dàng nâng cấp.
    + [wifi-iot-core-app](https://github.com/genuine-engineering/wifi-iot-core-app) App react native ví dụ mẫu cho `smartconfig`

- GSM/2G 
    + 
- LoraWan  - dự án lora-iot-core - Chưa xác định 
- Bluetooth LE - dự án ble-iot-core - Chưa xác định

### Gateway 

Một hệ thống IoT sẽ phục vụ rất nhiều kết nối, nếu chỉ dựa vào các Router hiện tại chỉ có khả năng phục vụ được Wifi, ngoài ra còn nhiều loại kết nối khác nữa. Đồng thời cần một số tính năng khi các End device trao đổi với nhau và tự động hóa khi mất kết nối Internet. Gateway base trên mã mở có thể giúp nhà phát triển bổ sung thêm những module, cũng như 
- Các phần cứng liên quan đến OpenWRT - Cần thảo luận thêm 

### FOTA Service 

- React - Redux front end cho user đăng nhập, tải firmware lên 
- S3 lưu trữ front end code 
- S3 lưu trữ firmware 
- Lambda cho API call 
- Congitive cho User login (Facebook/Google/User-pass)
- Bootloader + Module downloader hỗ trợ wifi/lora/ble/gms iot-core 
- API Gateway cho Lambda 
- Cloudfront cho S3 
- Database DynamoDb 
- Setup SSL

### Protocol 

- Khởi động dự án MQTT `libemqtt` port từ contiki, hỗ trợ wrap sang các MCU khác dễ dàng như ESP32/ESP8266/STM32/NRF5x
- Port `mbedtls` cho các nền tảng Hardware
- Thiết kế chuẩn hóa các model điều khiển phổ biến  

### Application API service

- Tương tự như FOTA Service 
- Thực thi các API setup AWS IoT bằng GUI (react front end)

### Mobile Application
- Mobile App dùng React native, có thể login dùng Google/Facebook/User-Pass, hỗ trợ BLE, hỗ trợ smartconfig
- Hỗ trợ kết nối Realtime (MQTT, Websocket)


### Realtime Service 

- Sử dụng AWS IoT, IBM Bluemix 
- Sử dụng emqtt broker, mosquito, mosca 