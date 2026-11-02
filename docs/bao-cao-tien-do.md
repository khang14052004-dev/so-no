# Báo cáo tiến độ (anh nhắn "Báo cáo")

Lập 30/10/2026 theo lời anh dặn: anh nhắn **"Báo cáo"** ở bất kỳ phiên nào thì Claude gửi báo cáo tiến độ Done Nha theo mẫu dưới, gồm: việc đã xong, việc tiếp theo, % tiến độ, việc bị trễ.

## Cách làm mỗi lần
1. Đọc nguồn: `docs/ke-hoach-tuan.md` (việc theo tuần, dấu [x]), mục "Chốt" mới nhất và "Còn mở" trong `CLAUDE.md`, `git log` của `so-no` và `done-nha` kể từ ngày của "Bản mới nhất".
2. Sửa cột "Xong" ở bảng trọng số cho đúng hôm nay, tính lại %.
3. Xét trễ và rủi ro theo luật ở dưới.
4. Gửi báo cáo trong chat theo mẫu (tiếng Việt, ngắn, có bảng).
5. Ghi đè mục "Bản mới nhất", thêm một dòng vào "Lịch sử %", commit.

Phiên không có repo (vd chat claude.ai): gửi "Bản mới nhất" trong file này nếu đọc được, nói rõ đó là số của ngày nào.

## Cách tính %
Tính theo khối lượng kế hoạch: mỗi tuần kế hoạch là 1 phần; pha 1 thiết kế (13–25/10) 2 phần, pha 2 (26/10–28/12) 9 phần, tổng 11. Việc "code xong, chờ anh thử máy thật" vẫn tính xong, kèm ghi chú.

| Tuần | Gói việc | Trọng số | Xong 2/11 |
|---|---|---|---|
| Pha 1 | Thiết kế: canvas, Design System, bàn giao | 2 | 2 |
| 26/10–1/11 | Khung app, đăng nhập khách + Google, Giữ chỗ, thẻ mời + Zalo | 1 | 1 |
| 2–8/11 | Tạo nhóm, mời, vào nhóm, Lịch, Xấp hình, khoản chi | 0,6 | 0,6 |
| 2–8/11 | Hình hóa đơn (chụp, nén, tải lên, xem, xóa) | 0,25 | 0,2 (chụp, nén, tải lên, xem xong 31/10, chờ thử máy thật; còn Xóa/Thêm ở chi tiết khoản) |
| 2–8/11 | Ghi khi mất mạng, đồng bộ sau | 0,15 | 0 |
| 9–15/11 | Góp quỹ, Số dư, Quỹ, Cân đối, Khóa | 0,6 | 0,6 (chờ thử máy thật) |
| 9–15/11 | Tài khoản nhận tiền + VietQR | 0,4 | 0 |
| 16–22/11 | Sổ nợ tổng, Ghi nhanh, Ghi trả, Sổ riêng, kiểu D, Cấn trừ | 1 | 0 |
| 23–29/11 | Báo nợ, trang xem sổ, Chia bill | 1 | 0 |
| 30/11–6/12 | Thống kê, Tôi, Quyền riêng tư, CSV, mất mạng/gửi lỗi/sửa trùng, trang chủ + Chính sách quyền riêng tư (Google Publish) | 1 | 0 |
| 7–13/12 | Thử kín cả nhóm, sửa lỗi | 1 | 0 |
| 14–20/12 | Tổng kết chuyến, xóa chuyến dọn hình | 1 | 0 |
| 21–28/12 | Sửa lỗi, hướng dẫn cài, tạo chuyến Đà Lạt thật | 1 | 0 |
| **Tổng** | | **11** | **4,4 = 40%** |

- Thiết kế % = phần pha 1 xong ÷ 2. Code % = phần pha 2 xong ÷ 9.
- Thời gian đã qua = (hôm nay − 13/10) ÷ 76 ngày (13/10 → 28/12).
- Sớm/chậm = (% xong − % thời gian) × 76 ngày. Dương là sớm.

## Luật xét trễ
- **Trễ:** việc có hạn (tuần kế hoạch, mốc pha) đã qua mà chưa xong. Ghi ai đang giữ (Anh / Claude) và trễ mấy ngày.
- **Đang chờ:** việc của anh chưa có hạn, ghi từ ngày nào.
- **Rủi ro:** chưa trễ nhưng chặn mốc sau; ghi "cần trước ngày nào".
- Mốc cứng: thử kín 7–13/12 · Google Publish trước 7/12 · ngừng thêm tính năng 20/12 · sẵn sàng 28/12 · Supabase Free (giữ hoạt động hoặc lên Pro) trước 28/12 · đi Đà Lạt 2/1/2027.

## Mẫu báo cáo
1. Một dòng: **X%** (thiết kế Y%, code Z%) · thời gian đã qua T% · sớm/chậm N ngày.
2. Đã xong (từ lần báo cáo trước; lần đầu thì tóm tắt tất cả).
3. Tiếp theo: Claude (thứ tự, model) và Anh.
4. Trễ (ai giữ, mấy ngày) và việc đang chờ anh.
5. Rủi ro sắp tới (bảng: việc, cần trước, vì sao).

## Bản mới nhất (2/11/2026)
**40%** (thiết kế 100%, code 27%) · thời gian đã qua 26% · **sớm khoảng 10 ngày** (30/10 sớm ~12 ngày; 30–31/10 dồn sức làm lại giao diện Xấp hình và Thêm khoản chi theo góp ý, không cộng thêm khối lượng mới).

Đã xong (30/10 → 2/11):
- Xấp hình kiểu cổ điển theo Figma của anh: chữ viết tay Italianno, giá trên mảnh giấy có kẹp, ngày giờ ghi khoản, thẻ cùng chiều cao; khoản chưa có hình dùng sticker vẽ tay.
- Bộ sticker Hand-drawn Flat Color (bản màu B, không bóng): 30 sticker, Ăn uống có thêm ly trà đá; gói `done-nha-icon-figma.zip` (sticker + 65 icon Phosphor) đã chép vào `03-assets/icons-figma`.
- Thêm khoản chi làm lại theo wireframe Figma 10:2954: một thẻ polaroid lớn, bấm thẳng lên thẻ để gõ giá, tên, ngày; ô xổ Chia và Ai trả; camera chạy ngay trong khung hình; thẻ tự co theo màn để hàng loại khoản luôn thấy.
- Hình hóa đơn: nén trên máy, tải lên kho, Xấp hình hiện hình thật, sửa khoản / Hoàn tác xóa chuyển hình theo.
- Design System bản 47 (59 màu), 40 bài kiểm JS, 151 kiểm tra SQL.

Tiếp theo:
- Claude: (1) Hình hóa đơn phần còn lại: xem hình lớn, Thêm/Xóa hình ở chi tiết khoản, nhắc che tên/SĐT đơn Grab (Opus); (2) Ghi khi mất mạng, đồng bộ sau (Opus, hạn tuần này 8/11); (3) Tài khoản nhận tiền + VietQR (Opus, 9–15/11); (4) Sổ nợ tổng (16–22/11, Sonnet theo khuôn, Opus khi đụng tính tiền).
- Anh: thử trên điện thoại Chụp bill (camera trong thẻ), Up hình, lưu rồi xem hình trên Xấp hình; dán `schema.sql` (commit be75d74) nếu chưa; thử Góp quỹ → Đã nhận → Khóa → Done nha trên 2 máy; chọn hàng loại khoản (giữ Chỗ ở, Đồ mang theo hay đổi Cà phê, Đi chợ như wireframe); nhờ một bạn iPhone (Chrome) thử trọn luồng, nhất là camera.

Trễ: Claude không có việc trễ. Anh trễ 8 ngày so với hạn pha 1 (25/10): duyệt bàn giao Lịch, đọc duyệt bàn giao Vào nhóm (hai màn đã code và thử đạt, đề xuất đóng). Đang chờ anh: dán schema be75d74, thử Góp quỹ/Cân đối máy thật, ô ngày trên iPhone (từ 29/10); bạn iPhone thử (từ 28/10); thử Chụp bill và chọn hàng loại khoản (từ 31/10).

Rủi ro: camera trong trang và gửi hình chưa thử trên iPhone thật (cần trước thử kín 7/12); biểu tượng app + màu chủ đạo (cần trước ~30/11, icon tạm "DN"); trang chủ + Chính sách quyền riêng tư để Google Publish (trước 7/12); "Mở bằng Chrome" từ Zalo trên iPhone chưa thử; Supabase Free tự ngủ khi ít dùng (chọn cách giữ hoặc lên Pro trước 28/12); hình mảnh giấy chưa rõ giấy phép (kiểm trước khi lên cửa hàng); canvas còn chữ và Xấp bản cũ (không chặn).

## Lịch sử %
| Ngày | Tổng | Thiết kế | Code | Thời gian | Sớm/chậm |
|---|---|---|---|---|---|
| 30/10 | 38% | 100% | 24% | 22% | sớm ~12 ngày |
| 2/11 | 40% | 100% | 27% | 26% | sớm ~10 ngày |
