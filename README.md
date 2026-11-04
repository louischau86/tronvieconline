[README.md](https://github.com/user-attachments/files/34351588/README.md)
# Trốn việc 8h–17h

Game mô phỏng một ngày công sở: lén lướt Facebook, nhắn Zalo rồi kịp quay về Excel trước khi sếp tới. Cân bằng giữa chăm chỉ và vui vẻ, né ba lần cảnh cáo và sống sót đến 17:00.

**Chơi ngay:** [https://gameduaxe2s-cpu/tronvieconline.github.io](https://gameduaxe2s-cpu.github.io/tronvieconline/)

## Cách chơi

Một ngày làm việc kéo dài khoảng 90 giây ngoài đời thực, tương ứng từ 08:00 đến 17:00 trong game.

- Nhấn **Space** (hoặc bấm nút lớn bên dưới) để chuyển qua lại giữa bảng tính Excel và Facebook.
- Lướt Facebook làm thanh **Vui vẻ** tăng nhưng thanh **Chăm chỉ** tụt. Làm việc thì ngược lại.
- Khi nghe tiếng bước chân và thấy cảnh báo, hãy quay về Excel trước khi sếp đứng sau lưng.
- Tin nhắn Zalo thỉnh thoảng hiện lên. Bấm vào để được +12 vui vẻ, nhưng nếu lúc đó sếp đang ở sau lưng thì bạn bị cảnh cáo.

### Điều kiện thua

- Bị sếp bắt gặp ba lần.
- Thanh Chăm chỉ về 0 (bị đuổi vì lười).
- Thanh Vui vẻ về 0 (kiệt sức, nộp đơn nghỉ việc).

### Tính điểm

Điểm chill tăng khi bạn lướt mạng mà không bị bắt gặp, và cộng thêm mỗi lần trả lời Zalo kịp lúc. Cuối ván, nhập tên để lưu điểm hoặc bấm **Chia sẻ điểm** để dán kết quả vào nhóm chat.

## Tính năng

- Chạy hoàn toàn trên trình duyệt, chỉ cần một file `index.html`, không cần cài đặt hay thư viện ngoài.
- Âm thanh tạo bằng Web Audio: bước chân của sếp, chuông cảnh cáo, nhạc thắng và thua. Có nút bật tắt tiếng.
- Hình minh họa vẽ bằng SVG: văn phòng, cửa phòng sếp, màn hình đổi theo chế độ.
- Hỗ trợ giao diện sáng và tối theo cài đặt của thiết bị, dùng được trên điện thoại.
- Bảng điểm cao lưu trong trình duyệt của mỗi người chơi, kèm nút chia sẻ điểm.

## Đưa lên GitHub Pages

1. Tạo repository mới ở chế độ Public.
2. Tải file `index.html` (và `README.md` này) lên repository.
3. Vào **Settings → Pages**, ở mục **Source** chọn **Deploy from a branch**, chọn nhánh `main` và thư mục `/ (root)`, rồi bấm **Save**.
4. Chờ một đến hai phút, trang sẽ có mặt tại `https://TEN-CUA-BAN.github.io/TEN-REPO/`.

## Chạy trên máy

Mở trực tiếp file `index.html` bằng trình duyệt. Không cần máy chủ.

## Tùy chỉnh

Các thông số cân bằng game nằm trong hàm `loop` của `index.html`:

| Thông số | Vị trí trong code | Mặc định |
| --- | --- | --- |
| Tốc độ làm việc, lướt mạng | `S.dil`, `S.fun` trong `loop` | làm việc +4 chăm chỉ/giây, lướt mạng −5 chăm chỉ/giây |
| Tần suất sếp xuất hiện | `S.bt` | 3 đến 9 giây giữa các lần |
| Thời gian cảnh báo trước khi sếp tới | `Math.max(.7,1.6-prog*.8)` | 1,6 giây, giảm dần còn 0,7 giây |
| Tần suất tin Zalo | `zaloTick` | khoảng 9 đến 17 giây một lần |
| Độ dài một ván | `S.t+=dt*6` | 6 phút trong game mỗi giây thực |

## Giới hạn

Bảng điểm trong bản này chỉ lưu cục bộ trên từng thiết bị. Muốn có bảng xếp hạng chung giữa nhiều người chơi, bạn cần nối thêm một dịch vụ lưu dữ liệu như Firebase hoặc Supabase.

## Giấy phép

