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

| Tuần | Gói việc | Trọng số | Xong 30/10 |
|---|---|---|---|
| Pha 1 | Thiết kế: canvas, Design System, bàn giao | 2 | 2 |
| 26/10–1/11 | Khung app, đăng nhập khách + Google, Giữ chỗ, thẻ mời + Zalo | 1 | 1 |
| 2–8/11 | Tạo nhóm, mời, vào nhóm, Lịch, Xấp hình, khoản chi | 0,6 | 0,6 |
| 2–8/11 | Hình hóa đơn (chụp, nén, tải lên, xem, xóa) | 0,25 | 0 |
| 2–8/11 | Ghi khi mất mạng, đồng bộ sau | 0,15 | 0 |
| 9–15/11 | Góp quỹ, Số dư, Quỹ, Cân đối, Khóa | 0,6 | 0,6 (chờ thử máy thật) |
| 9–15/11 | Tài khoản nhận tiền + VietQR | 0,4 | 0 |
| 16–22/11 | Sổ nợ tổng, Ghi nhanh, Ghi trả, Sổ riêng, kiểu D, Cấn trừ | 1 | 0 |
| 23–29/11 | Báo nợ, trang xem sổ, Chia bill | 1 | 0 |
| 30/11–6/12 | Thống kê, Tôi, Quyền riêng tư, CSV, mất mạng/gửi lỗi/sửa trùng, trang chủ + Chính sách quyền riêng tư (Google Publish) | 1 | 0 |
| 7–13/12 | Thử kín cả nhóm, sửa lỗi | 1 | 0 |
| 14–20/12 | Tổng kết chuyến, xóa chuyến dọn hình | 1 | 0 |
| 21–28/12 | Sửa lỗi, hướng dẫn cài, tạo chuyến Đà Lạt thật | 1 | 0 |
| **Tổng** | | **11** | **4,2 = 38%** |

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

## Bản mới nhất (30/10/2026)
**38%** (thiết kế 100%, code 24%) · thời gian đã qua 22% · **sớm khoảng 12 ngày**.

Đã xong:
- Thiết kế: canvas bản 224 (115 bảng), Design System bản 32 (54 màu), bàn giao Lịch và Vào nhóm.
- App chạy ở `done-nha.pages.dev`: khung PWA (tự nhận bản mới), thẻ mời + Zalo, chọn tên, tự thêm tên, Giữ chỗ + Lưu bằng Google, Đăng nhập Google, Tạo nhóm, Mời (QR, Đổi link), Mở lại tên, Lịch, Xấp hình, thêm/sửa/xóa khoản chi, Góp quỹ, Số dư, Quỹ, Cân đối, Khóa (nhóm không quỹ: chủ nhóm khóa), rà soát chữ (bớt 36% chữ).
- Kiểm thử: 151 kiểm tra SQL, 38 bài kiểm JS. Đã thử máy thật đạt: thẻ mời, chọn tên, Google, Tạo nhóm/Mời, Lịch + khoản chi.

Tiếp theo:
- Claude: (1) Hình hóa đơn, (2) Ghi khi mất mạng, (3) Tài khoản nhận tiền + VietQR, (4) Sổ nợ tổng (tuần 16–22/11). Đều Opus, trừ phần Sổ nợ theo khuôn.
- Anh: dán `schema.sql` (commit be75d74) nếu chưa; thử Góp quỹ → Đã nhận → Khóa → Done nha trên 2 máy (1 máy thủ quỹ) và khóa ở nhóm không quỹ; xem lại ô ngày trên iPhone; nhờ một bạn iPhone (Chrome) thử trọn luồng.

Trễ: Claude không có việc trễ. Anh trễ 5 ngày so với hạn pha 1 (25/10): duyệt bàn giao Lịch, đọc duyệt bàn giao Vào nhóm (hai màn đã code và thử đạt, đề xuất đóng). Đang chờ anh từ 28–29/10: dán schema, thử máy thật Góp quỹ/Cân đối, ô ngày iPhone, bạn iPhone thử.

Rủi ro: biểu tượng app + màu chủ đạo (cần trước ~30/11, thử kín phải cài vào màn hình chính, giờ icon tạm "DN"); trang chủ + Chính sách quyền riêng tư để Google Publish (trước 7/12); "Mở bằng Chrome" từ Zalo trên iPhone chưa thử; Supabase Free tự ngủ (trước 28/12); canvas còn chữ cũ (không chặn).

## Lịch sử %
| Ngày | Tổng | Thiết kế | Code | Thời gian | Sớm/chậm |
|---|---|---|---|---|---|
| 30/10 | 38% | 100% | 24% | 22% | sớm ~12 ngày |
