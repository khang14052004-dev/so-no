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
Tính theo khối lượng kế hoạch: mỗi tuần kế hoạch là 1 phần; pha 1 thiết kế (13–25/10) 2 phần, pha 2 (26/10–28/12) 9 phần, tổng 11. **Từ 17/11 thêm 0,5 phần cho gói sửa Auth P0 (việc chen ngang 16–17/11), pha 2 thành 9,5, tổng 11,5**; vì vậy % từ 17/11 thấp hơn cách tính cũ khoảng 1 điểm. Việc "code xong, chờ anh thử máy thật" vẫn tính xong, kèm ghi chú.

| Tuần | Gói việc | Trọng số | Xong 27/11 |
|---|---|---|---|
| Pha 1 | Thiết kế: canvas, Design System, bàn giao | 2 | 2 |
| 26/10–1/11 | Khung app, đăng nhập khách + Google, Giữ chỗ, thẻ mời + Zalo | 1 | 1 |
| 2–8/11 | Tạo nhóm, mời, vào nhóm, Lịch, Xấp hình, khoản chi | 0,6 | 0,6 |
| 2–8/11 | Hình hóa đơn (chụp, nén, tải lên, xem, xóa) | 0,25 | 0,25 (xong 2/11, anh thử máy thật đạt) |
| 2–8/11 | Ghi khi mất mạng, đồng bộ sau | 0,15 | 0,15 (xong 3/11, anh thử S24 đạt) |
| 9–15/11 | Góp quỹ, Số dư, Quỹ, Cân đối, Khóa | 0,6 | 0,6 (chờ thử máy thật) |
| 9–15/11 | Tài khoản nhận tiền + VietQR | 0,4 | 0,4 (quét bằng app ngân hàng thật đạt 25/11) |
| 16–22/11 | Sổ nợ tổng, Ghi nhanh, Ghi trả, Sổ riêng, kiểu D, Cấn trừ | 1 | 0,95 (thử Staging đạt; lỗi 1, 3, 4 sửa và anh thử lại đạt 25/11; lỗi 5 màu avatar sửa 25/11; Cấn trừ và gộp nơi để sau chuyến; chưa gộp `main`) |
| 23–29/11 | Báo nợ, trang xem sổ, Chia bill | 1 | 0,8 (Chia bill + Ghi nợ vào Sổ riêng xong, lỗi 7 anh thử lại đạt 25/11; Báo nợ máy thật đạt với dữ liệu giả, chưa thử dữ liệu thật trên Staging; trang xem sổ để sau chuyến (Q6)) |
| 30/11–6/12 | Thống kê, Tôi, Quyền riêng tư, CSV, mất mạng/gửi lỗi/sửa trùng, trang chủ + Chính sách quyền riêng tư (Google Publish) | 1 | 0,7 (S5 Thống kê trên Staging, chờ đối chiếu số; S6 Tôi + Xuất CSV + Quyền riêng tư đã push 25/11, CSV đạt LibreOffice và Android, Lưu bằng Google đạt, còn tải CSV trên iPhone; Xóa tài khoản trong app + chuyển quyền chủ nhóm + bàn giao thủ quỹ xong 26/11, migration đã áp Staging, chưa thử máy thật; S2 Chính sách chờ email thật, kiểm Data Access) |
| Chen ngang 16–17/11 | Sửa Auth P0 (A1–A3, Q12 khoản cần xử lý): rà soát, phương án, bản vẽ, lõi thuần | 0,5 | 0,15 (đặc tả + bản vẽ Q12 xong; `authGate.js` + `quarantine.js` thuần 29 bài kiểm, nhánh `auth-p0-logic` chưa push; nối vào app + thử thật sau 29/11) |
| 7–13/12 | Thử kín cả nhóm, sửa lỗi | 1 | 0 |
| 14–20/12 | Tổng kết chuyến, xóa chuyến dọn hình | 1 | 0 |
| 21–28/12 | Sửa lỗi, hướng dẫn cài, tạo chuyến Đà Lạt thật | 1 | 0 |
| **Tổng** | | **11,5** | **7,55 = 66%** |

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

## Bản mới nhất (27/11/2026)
**66%** (thiết kế 100%, code 58%) · thời gian đã qua 59% · **sớm khoảng 5 ngày**.

Đã xong (25/11 → 27/11), tất cả trên `so-no-moi` + bản xem trước Staging, `main` và Production không đổi:
- **S6 Tôi** `/toi` đã push (`6edfdaa`): thẻ hồ sơ + trạng thái đồng bộ, Tài khoản nhận tiền + Mã QR, Xuất CSV một sổ một file, Quyền riêng tư, Ghi nhanh. Thử thật: CSV đạt trên LibreOffice và Android (mở bằng Google Sheets), Lưu bằng Google trên Staging đạt.
- **Xóa tài khoản trong app** (thay Q7 "chỉ ghi liên hệ"): kiểm sạch nợ mọi nhóm, 3 chặng (Không thể hoàn tác → Sổ riêng còn nợ → gõ XÓA), Xuất CSV ngay trong trang, sticker vẽ tay, hình đầu chặng 145px. Kèm **chuyển quyền chủ nhóm + bàn giao thủ quỹ** ở Cài đặt nhóm. Migration `20261126000000_xoa_tai_khoan` anh đã áp Staging (22 kiểm tra SQL mới).
- **Nút quay lại về đúng màn trước** cho Tài khoản, Mã QR, Sổ nợ, Báo nợ, Tôi, Xóa tài khoản (mở thẳng bằng link thì về màn cha).
- Lỗi 5 màu avatar sửa; anh thử lại lỗi 1, 3, 4, 7 đạt; VietQR quét bằng app ngân hàng thật đạt.
- Kiểm: `npm test` 216/216, kiểm SQL đạt, bài kiểm giao diện Xóa tài khoản 31/31 và nút quay lại 19/19 ở 360/412px.

Đang làm:
| Việc | Xong | Còn |
|---|---|---|
| S6 Tôi | code 100% | anh tải CSV trên iPhone thì đóng |
| Xóa tài khoản + chuyển quyền, bàn giao | code 100% | anh thử trên Staging; migration Production sau 30/11 |
| S5 Thống kê | code 100% | anh đối chiếu số trên Staging |
| Nút quay lại màn nhóm A–E | 0% | chờ anh cho sửa trên `so-no-moi` hay để sau 29/11 |
| Hướng dẫn thêm vào màn hình chính iPhone có hình | bản nháp | đưa vào app cùng thanh nhắc cài, sau 29/11 |
| Gói Auth P0 (A1–A3 + Q12) | ~30% | nối vào app, thử thật: sau 29/11 |
| S2 Chính sách quyền riêng tư | ~70% | email liên hệ thật, đối chiếu Data Access, công bố |
| Chia theo món trong nhóm | ~20% | code từ 30/11 |
| UX Research A–E (anh) | anh giữ | đợt thử tới 28/11, chốt 29/11 |

Tiếp theo:
- Claude: (1) sửa theo góp ý khi anh thử Xóa tài khoản, S6 (Opus); (2) nút quay lại màn nhóm nếu anh cho; (3) từ 30/11: gộp `so-no-moi` (Opus review A–E, migration Production riêng), Auth P0, Chia theo món nhóm, lỗi (e)(f), lỗi 2, thanh nhắc cài + hướng dẫn iPhone có hình.
- Anh: thử Xóa tài khoản 3 chặng, chuyển quyền, bàn giao trên Staging; tải CSV trên iPhone; đối chiếu số S5; chốt UI/flow A–E 29/11.

Trễ:
- Claude: không có.
- Anh: duyệt bàn giao Lịch và Vào nhóm (trễ 33 ngày, đề xuất đóng).

Đang chờ anh:
- Thử Xóa tài khoản + chuyển quyền + bàn giao trên Staging (từ 26/11)
- Tải CSV trên iPhone để đóng S6 (từ 25/11)
- Đối chiếu số S5 trên Staging (từ 23/11)
- Chọn email liên hệ riêng cho Done Nha (Chính sách, Google Publish) (từ 25/11)
- Nút quay lại màn nhóm: sửa ngay trên `so-no-moi` hay sau 29/11 (từ 26/11)
- Thử Góp quỹ/Cân đối máy thật, ô ngày iPhone (từ 29/10)

Rủi ro:
| Việc | Cần trước | Vì sao |
|---|---|---|
| Gộp `so-no-moi` vào `main` | 30/11 | Production thiếu nhiều migration (Sổ riêng, cài đặt, xóa tài khoản): sao lưu, đối chiếu, duyệt riêng |
| Tuần 30/11–6/12 quá tải | 6/12 | Gộp nhánh, sửa A–E sau nghiên cứu, Auth, Chia theo món, lỗi (e)(f), thanh nhắc cài, hardening |
| Auth thật (mức 2, iPhone) | 7/12 | Chưa thử iPhone thì không phát hành |
| Trang chủ + Chính sách công bố | 7/12 | Google Publish; cần email thật |
| Supabase Free (2 dự án tự ngủ) | 28/12 | Giữ hoạt động hoặc lên Pro |
| Pháp lý (chưa hỏi luật sư) | trước mở cho người ngoài nhóm bạn | Luật BVDLCN, STK |

## Lịch sử %
| Ngày | Tổng | Thiết kế | Code | Thời gian | Sớm/chậm |
|---|---|---|---|---|---|
| 30/10 | 38% | 100% | 24% | 22% | sớm ~12 ngày |
| 2/11 | 40% | 100% | 27% | 26% | sớm ~10 ngày |
| 10/11 | 46% | 100% | 34% | 37% | sớm ~7 ngày |
| 11/11 | 46% | 100% | 34% | 38% | sớm ~6 ngày |
| 12/11 | 54% | 100% | 43% | 39% | sớm ~11 ngày |
| 15/11 | 56% | 100% | 46% | 43% | sớm ~9 ngày |
| 17/11 | 56% | 100% | 46% | 46% | sớm ~7 ngày (tổng 11,5) |
| 18/11 | 58% | 100% | 49% | 47% | sớm ~8 ngày |
| 19/11 | 59% | 100% | 50% | 49% | sớm ~8 ngày |
| 20/11 | 59% | 100% | 50% | 50% | sớm ~7 ngày |
| 23/11 | 60% | 100% | 51% | 54% | sớm ~4 ngày |
| 25/11 | 61% | 100% | 53% | 57% | sớm ~4 ngày |
| 27/11 | 66% | 100% | 58% | 59% | sớm ~5 ngày |
