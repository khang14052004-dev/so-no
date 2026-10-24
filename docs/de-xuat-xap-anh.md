# Đề xuất: "Xấp ảnh" cho Lịch chuyến đi

Ngày 24/10/2026. Trạng thái: **anh đã chốt 6 câu (24/10 trưa), đã vẽ bản đầu trên canvas bản 211.** Mục "Đã chốt" bên dưới thay cho các chỗ đề xuất cũ nếu khác.

## Sửa theo góp ý của anh (24/10 chiều, thay các ý 2, 3 và dải mở ngày bên dưới nếu khác)
- Bỏ thẻ "+N" và bỏ bước "mở xấp thành dải". Mỗi ngày là MỘT hàng thẻ polaroid nghiêng, **vuốt ngang** (thẻ thứ ba ló ra một phần để gợi ý). Mọi khoản đều có thẻ; giữ góc nghiêng cũ (thẻ 1 thẳng, thẻ chẵn −3 đến −5°, thẻ lẻ +3 đến +5°).
- Bấm thẻ mở **thẳng trang chi tiết khoản** (không còn "Thu gọn", không còn dải 1/6).
- **Giá đóng mộc lên ảnh**, cùng kiểu dấu "Done nha ✓" ở Tổng kết (viền xanh, xoay −6°, nền kem đặc để đọc trên mọi ảnh), góc dưới phải. Ghi gọn (`870k`, `1,2tr`). Thẻ chữ (không ảnh) cũng có mộc.
- Tên khoản nằm dưới ảnh, chữ nhạt `ink-2`, một dòng. Thay ý cũ "số tiền chỉ ở thẻ trên cùng, không đặt lên ảnh".
- Bảng `DN-Chuyen-Xap-MoNgay` đổi thành `DN-Chuyen-Xap-ChiTiet` (bấm thẻ ra chi tiết khoản). Design System: PhotoStack bản 20.

## Đã chốt (anh đồng ý hết, 24/10 trưa; theo nghiên cứu sâu)
1. Thứ tự: **Trước chuyến → Ngày 1 → ngày cuối**, đọc như câu chuyện; đang đi thì đánh dấu "Hôm nay" (app thật tự cuộn tới).
2. **3 thẻ** mỗi xấp; từ 4 khoản thì thẻ thứ 3 thành "+N" mờ.
3. **Số tiền chỉ ở thẻ trên cùng** (thẳng 0°, dải trắng dưới ảnh); các thẻ sau để dải trống; tổng ngày ghi bằng chữ thẳng bên phải tiêu đề, kèm viên mức "~k/người" (Trước chuyến không có viên mức).
4. **Polaroid** (khung trắng, dải đáy).
5. Nhóm dài hạn (Cơm trưa) **chưa dùng Xấp**; để sau chuyến.
6. **Tổng kết chuyến**: vẽ 1 bảng phác (ảnh story 9:16, không ghi ai nợ ai); làm thật tuần 14–20/12 bằng canvas, tạo sẵn ảnh trước khi bấm Chia sẻ.
- Nút đổi kiểu "Xấp ảnh | Lịch tháng" ở đầu mục Lịch; chuyến mặc định Xấp. Thẻ đầu ở kiểu Xấp: "4 ngày đi · cả nhóm" thay cho "Tháng này".
- Bấm xấp: mở tại chỗ thành dải thẻ vuốt ngang (có "1/6"), bấm thẻ mở chi tiết khoản; nút "Thu gọn". Ngày chưa tới: khung nét đứt `cal-trip-edge` "Sắp tới"; ngày đã qua mà trống: nút "Chưa có khoản nào · Ghi khoản".
- Thẻ chữ dùng màu token có sẵn theo loại (Ăn uống `warn-tint`, Chỗ ở `blue-wash`, Đi lại `success-tint`, Đồ mang theo `yellow-tint`, Vé và chơi `blue-tint`, Khác `fill-quiet`); token riêng cho loại khoản chờ anh chốt.
- Bản thử: Tôi › Bản thử › "Giả lập đang đi Đà Lạt" (hôm nay 4/1, 11 khoản của 3 ngày đầu, 6 ảnh).
- Nghiên cứu sâu 24/10 (báo cáo trong phiên): chưa app chia tiền lớn nào lấy ảnh làm giao diện chính; iOS 18+ làm được bằng CSS gốc (transform, scroll-snap, View Transitions); xấp chỉ dùng ảnh nhỏ 15 KB; chuyến từ 8 ngày thêm chip chọn ngày, quá 14 ngày mặc định Lịch tháng; tổng kết vẽ bằng canvas 1080×1920, chia sẻ bằng Web Share (không `await` trước `share()`).

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

## Câu hỏi đã trả lời
Xem mục "Đã chốt" ở đầu file.

## Bảng cần vẽ (khi duyệt)
`DN-Chuyen-Xap` (mặc định), `DN-Chuyen-Xap-MoNgay` (mở một xấp), `DN-Chuyen-Xap-ItAnh` (toàn thẻ chữ), `DN-Chuyen-Xap-TruocChuyen`, `DN-Chuyen-DaiNgay` (kiểu Lịch thu gọn). Thêm thành phần `PhotoStack` vào Design System.
