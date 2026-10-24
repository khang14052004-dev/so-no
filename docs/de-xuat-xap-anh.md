# Đề xuất: "Xấp ảnh" cho Lịch chuyến đi

Ngày 24/10/2026. Trạng thái: **hướng đã chọn (anh muốn), chi tiết chờ duyệt, CHƯA vẽ trên canvas.** Nghiên cứu sâu đang chạy; có kết quả thì bổ sung mục "Nghiên cứu".

## Anh muốn gì (lời anh, 24/10)
- Chuyến đã có ngày đi và ngày về, nên nếu cả chuyến nằm trong một tháng thì bỏ phần tháng cho đỡ tốn chỗ.
- Một ngày có nhiều bữa, nhiều chỗ chi; lưới tháng hiện tại chỉ thấy ảnh mới nhất mỗi ngày, không đa dạng, không đẹp.
- Muốn kiểu xếp ảnh lạ mắt (2 ảnh mẫu: ảnh polaroid xếp theo ngày; thẻ nghiêng xếp chồng có thẻ "+12" mờ, có nút đổi kiểu xem ở góc dưới) để thu hút người dùng và dễ phát triển về sau.
- Ảnh mẫu chỉ để tham khảo, không làm giống.

## So sánh 3 kiểu

| Kiểu | Được | Mất |
|---|---|---|
| **Xấp theo ngày (đề xuất, mặc định cho chuyến)** | Lạ mắt, thấy 3–4 khoản mỗi ngày, đọc như nhật ký chuyến, mở đường cho "Tổng kết chuyến" để chia sẻ | Dài hơn lưới; khi ít ảnh phải có thẻ chữ đẹp |
| Lưới tháng (hiện tại, bản 208) | Gọn, hợp nhóm dài hạn như Cơm trưa | Mỗi ngày một ảnh; chuyến 4 ngày mà chiếm cả tháng |
| Dải ngày chuyến (lưới thu gọn) | Gọn nhất | Vẫn một ảnh mỗi ngày |

Đề xuất: chuyến mặc định **Xấp**, có nút đổi sang **Lịch** (dạng dải ngày chuyến, không cả tháng). Nhóm dài hạn giữ Lịch tháng mặc định, đổi sang Xấp được.

## Chi tiết đề xuất
- **Khối ngày:** tiêu đề trái "Ngày 2 · Thứ Bảy 3/1"; phải "1,2tr · ~150k/người" kèm chấm màu mức (`cal-low/mid/high`, cùng ngưỡng 100k / 500k).
- **Xấp:** tối đa 4 thẻ, chồng lên nhau khoảng 1/3, nghiêng nhẹ (đề xuất −5° tới +5°). Góc nghiêng tính cố định theo id khoản, không nhảy khi tải lại. Hơn 4 khoản thì thẻ cuối là "+N" mờ.
- **Thẻ có ảnh:** khung kiểu polaroid trắng (`surface`, viền mỏng, đáy dày hơn); dải đáy ghi số tiền gọn bằng chữ Newsreader ("412k"). Dùng ảnh nhỏ ~15 KB đã có (`thumb_path`).
- **Thẻ không ảnh (thẻ chữ):** icon loại khoản, tên khoản (ghi chú), số tiền, "Kiệt trả". Nghiêng ít hơn (≤3°) để dễ đọc.
- **Bấm xấp:** mở ngay tại chỗ thành danh sách khoản của ngày (dòng có ảnh nhỏ), bấm lại để thu. Có thể vuốt ngang để lướt thẻ (chờ nghiên cứu).
- **Trước chuyến / Sau chuyến:** khối riêng cho đặt cọc, vé xe, đồ mang theo; khối "Sau chuyến" nếu có.
- **Ngày chưa tới hoặc chưa có khoản:** thẻ viền nét đứt "Chưa có khoản · + Ghi".
- **Thứ tự:** ngày mới nhất ở trên (giống ảnh mẫu, ghi xong thấy ngay). Câu hỏi: sau chuyến có đảo lại thành Ngày 1 → cuối như một câu chuyện không?
- **Nút đổi kiểu:** 2 icon "Xấp | Lịch" ở đầu mục Lịch. Không đặt ở đáy vì đáy đã có nút ghim "+ Ghi khoản chi".
- **Thẻ đầu:** giữ 3 số như hiện tại.
- **Tiếp cận:** mỗi xấp là một nút có nhãn đọc màn hình, ví dụ "Thứ Bảy 3/1, 6 khoản, cả nhóm 1,2 triệu". Bật giảm chuyển động thì bỏ nghiêng và hoạt ảnh.

## Dữ liệu
- Một chuyến chỉ vài chục khoản: máy khách đọc thẳng khoản chi + `entry_photos` của nhóm (RLS đã cho phép), gộp theo ngày giờ Việt Nam ngay trên máy. Chưa cần hàm SQL mới.
- Khoản cần **tên** để làm thẻ chữ: hiện dùng `note` và `category` của dòng sổ. Chưa có trường "nơi chi"; thêm sau nếu cần.

## Phát triển về sau
- **Tổng kết chuyến:** một ảnh dọc (khổ story) gồm các xấp của từng ngày, tổng tiền, số người, để chia sẻ lên Zalo hay Instagram. Đây là cách kéo người dùng mới (mỗi lần chia sẻ là một lần quảng cáo).
- Nhóm dài hạn dùng Xấp theo tuần.

## Câu hỏi chờ anh chốt
1. Sau chuyến có đảo thứ tự thành Ngày 1 → cuối không?
2. Khung polaroid hay thẻ bo góc (ảnh mẫu 2)? Em nghiêng về polaroid vì dải đáy ghi được số tiền.
3. Nhóm dài hạn có cần Xấp không, hay chỉ chuyến?

## Bảng cần vẽ (khi duyệt)
`DN-Chuyen-Xap` (mặc định), `DN-Chuyen-Xap-MoNgay` (mở một xấp), `DN-Chuyen-Xap-ItAnh` (toàn thẻ chữ), `DN-Chuyen-Xap-TruocChuyen`, `DN-Chuyen-DaiNgay` (kiểu Lịch thu gọn). Thêm thành phần `PhotoStack` vào Design System.
