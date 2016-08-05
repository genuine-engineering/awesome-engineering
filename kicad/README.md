# Summary

* [Giới thiệu Kicad](#kicad-introduction)
* [Các bước làm việc với Kicad](#kicad-workflow)
* [Thiết kế nguyên lý](#schematics)
* [Vẽ mạch in](#pcb)
* [Đồng bộ mạch nguyên lý và PCB](#annotation)
* [Tạo thư viện nguyên lý](#schematic-library)
* [Tạo thư viện chân PCB](#pcb-library)
* [Học Kicad từ Altium](#kicad-from-altium)
* [Những lưu ý, mẹo và nguồn tài liệu hữu ích khác](#tips-and-tricks)

## 1. [Giới thiệu KiCad](#kicad-introduction)

KiCad là một công cụ phần mềm thiết kế mạch nguyên lý và mạch in (PCB) trong lĩnh vực điện tử mã nguồn mở. Bên trong phần hệ thống phần mềm KiCad là những phần mềm chạy độc lập như sau:

| Tên chương trình | Mô tả                                                              | Đuôi mở rộng                    |
|------------------|--------------------------------------------------------------------|---------------------------------|
| KiCad            | Chương trình quản lý dự án KiCad                                   | *.pro                           |
| Eeschema         | Chương trình vẽ mạch (cả mạch nguyên lý và thư viện nguyên lý)     | *.sch, *.lib, *.net             |
| CvPcb            | Lựa chọn thư viện chân Footprint                                   | *.net                           |
| Pcbnew           | Chương trình vẽ mạch in PCB                                        | *.kicad_pcb                     |
| GerbView         | Gerber viewer                                                      | All the usual gerbers           |
| Bitmap2Component | Chương trình chuyển Bitmap thành PCB hay thư viện chân Footprint   | *.lib, *.kicad_mod, *.kicad_wks |
| PCB Calculator   | Tính toán cho linh kiện, độ rộng đường mạch, khoảng hở, mã màu ... | None                            |
| Pl Editor        | Page layout editor                                                 | *.kicad_wks                     |

> **Note** Danh sách file mở rộng trên chưa đầy đủ và chỉ chứa một phần các tập tin mà KiCad có thể làm việc, như vậy sẽ đơn giản và dễ nắm bắt hơn.

KiCad có thể đảm bảo độ tin cậy để phát triển thành công những sản phẩm điện tử phức tạp.

KiCad không giới hạn kích thước board mạch và dễ dàng sử dụng để thiết kế mạch lên tới 32 lớp, tới 14 lớp kỹ thuật và 4 lớp bổ trợ. KiCad có thể tạo tất cả các file cần thiết cho việc tạo nên tấm PCB, Gerber file cho máy Photo-Plotter (máy tạo Film chế bản), file khoan (drl hay NC), vị trí linh kiện (phục vụ SMT - cắm linh kiện bằng máy) và nhiều loại khác.

Bằng việc mở mã nguồn (giấy phép GPL), KiCad chính là công cụ lý tưởng cho các dự án có ý định mở mã nguồn phần cứng.

Trang chủ KiCad là: [http://wwww.kicad-pcb.org](http://wwww.kicad-pcb.org)

### 1.1. Tải và cài đặt KiCad

KiCad có thể chạy trên GNU/Linux, Apple OSX và Windows, bạn có thể tìm bản cài đặt phù hợp tại:
[http://www.kicad-pcb.org/download/](http://www.kicad-pcb.org/download/)

> **Warning** KiCad cho ra các phiên bản mới theo [chính sách xuất bản](http://ci.kicad-pcb.org/job/kicad-doxygen/ws/Documentation/doxygen/html/md_Documentation_development_stable-release-policy.html). Những tính năng mới liên tục được cập nhật vào nhánh development. Nếu bạn muốn trải nghiệm những tính năng mới đó và kiểm nghiệm giúp KiCad, hãy tải bản biên dịch nightly cho hệ điều hành của bạn. Bản biên dịch Nightly có khả năng có nhiều lỗi phát sinh, nhưng mục tiêu chính của Nhóm phát triển KiCad là luôn giữ cho nhánh Development trong trạng thái thử nghiệm, cho tới khi nào các tính năng được kiểm nghiệm hoàn chỉnh.

#### 1.2. GNU/Linux

##### Bản cài đặt ổn định

Bản cài đặt ổn định KiCad có thể tìm thấy tại hầu hết các trình quản lý gói cài đặt của bản phân phối Linux với tên gọi `kicad` và `kicad-doc`. Nếu bản phân phối của bạn không cung cấp bản cài đặt ổn định mới nhất, vui lòng làm theo hướng dẫn biên dịch, lựa chọn và cài đặt cho bản cài đặt chưa ổn định, nhưng lựa chọn bản ổn định, mới nhất.

##### Bản cài đặt chưa ổn định (Nightly developement)

Hầu hết đều được biên dịch từ mã nguồn mới nhất. Thỉnh thoảng xuất hiện các lỗi như hỏng file, tạo gerber sai, ... nhưng luôn có tính năng mới nhất.

Ở hệ điều hành Ubuntu, cách dễ nhất cài bản nightly build là sử dụng *PPA* và *Aptitude*. Thực hiện các lệnh sau trong Terminal:

```shell
sudo add-apt-repository ppa:js-reynaud/ppa-kicad
sudo aptitude update && sudo aptitude safe-upgrade
sudo aptitude install kicad kicad-doc-en
```

Với Fedora, cách dễ nhất thông qua *copr*

```shell
sudo dnf copr enable mangelajo/kicad
sudo dnf install kicad
```

Ngoài ra, có thể tải và cài đặt bản biên dịch trước của KiCad, hoặc tải trực tiếp mã nguồn, biên dịch và cài đặt

#### 1.3. Apple OS X

##### Bản cài đặt ổn định

Có thể tìm thấy [http://downloads.kicad-pcb.org/osx/stable/](http://downloads.kicad-pcb.org/osx/stable/)

##### Bản cài đặt chưa ổn định (Nightly developement)

Tải và cài đặt tại: [http://downloads.kicad-pcb.org/osx/nightly/](http://downloads.kicad-pcb.org/osx/nightly/)

#### 1.4. Windows

##### Bản cài đặt ổn định

Tải và cài đặt: [http://downloads.kicad-pcb.org/windows/stable/](http://downloads.kicad-pcb.org/windows/stable/)

##### Bản cài đặt chưa ổn định (Nightly developement)

Tải và cài đặt: [http://downloads.kicad-pcb.org/windows/nightly/](http://downloads.kicad-pcb.org/windows/nightly/)

#### 1.5. Thông tin hỗ trợ

Nếu bạn có ý tưởng, nhận xét hay bất kỳ câu hỏi nào, hay cần trợ giúp:
- Ghé thăm [diễn đàn](https://forum.kicad.info/)
- Tham gia [kênh #kicad IRC](http://webchat.freenode.net/?channels=kicad) trên Freenode
- Xem các [hướng dẫn](http://kicad-pcb.org/help/tutorials/)

## 2. [Tiến trình làm việc với KiCad](#kicad-workflow)

Mặc dù có sự tương đồng với những phần mềm thiết kế mạch khác, KiCad vẫn có đặc trưng bằng tiến trình công việc có sự phân biệt rõ ràng giữa 2 công cụ thiết kế nguyên lý và mạch in PCB.

### 2.1. Tổng quan tiến trình làm việc

Tiến trình làm việc với KiCad chia ra làm 2 phần chính là thiết kế nguyên lý và vẽ mạch in PCB. Cả 2 phần, thư viện nguyên lý và thư viện chân Footprint đều cần thiết cho cả 2 phần.

Trong hình dưới, là mô hình tiến trình làm việc hiện tại với KiCad, giải thích rõ ràng từng bước bạn cần phải thực hiện. Đồng thời các biểu tượng được thêm vào cho dễ dàng thực hiện.

![](images/kicad_flowchart.png)

Để có nhiều thông tin hơn về việc tạo thư viện nguyên lý, bạn có thể xem mục: [Tạo thư viện nguyên lý](./06.schematic-library.md). Và phần tạo thư viện chân Footprint linh kiện xem ở mục: [Tạo thư viện chân PCB](07.pcb-library.md).

### 2.2. Đồng bộ giữa mạch nguyên lý và PCB

Một mạch nguyên lý sau khi được vẽ đầy đủ thì bước tiếp theo phải chuyển sang vẽ PCB. Một bản mạch khi một khi muốn hoàn thiện thì trong quá trình vẽ có thể thêm và bớt linh kiện. Điều này có thể thực hiện theo 2 hướng: Tới và Lùi.

Việc đồng bộ Tới là tiến trình chuyển sự thay đổi từ mạch nguyên lý, và làm cho PCB đúng với nó. Điều này là cơ bản vì không ai muốn phải vẽ lại mạch PCB mỗi khi có thay đổi. Có thể xem thêm [Đồng bộ mạch nguyên lý và PCB](#annotation)

