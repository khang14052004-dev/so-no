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

| Tuần | Gói việc | Trọng số | Xong 23/11 |
|---|---|---|---|
| Pha 1 | Thiết kế: canvas, Design System, bàn giao | 2 | 2 |
| 26/10–1/11 | Khung app, đăng nhập khách + Google, Giữ chỗ, thẻ mời + Zalo | 1 | 1 |
| 2–8/11 | Tạo nhóm, mời, vào nhóm, Lịch, Xấp hình, khoản chi | 0,6 | 0,6 |
| 2–8/11 | Hình hóa đơn (chụp, nén, tải lên, xem, xóa) | 0,25 | 0,25 (xong 2/11, anh thử máy thật đạt) |
| 2–8/11 | Ghi khi mất mạng, đồng bộ sau | 0,15 | 0,15 (xong 3/11, anh thử S24 đạt) |
| 9–15/11 | Góp quỹ, Số dư, Quỹ, Cân đối, Khóa | 0,6 | 0,6 (chờ thử máy thật) |
| 9–15/11 | Tài khoản nhận tiền + VietQR | 0,4 | 0,4 (code xong 4/11; schema đã có trên Supabase 11/11; chờ quét thử app ngân hàng thật) |
| 16–22/11 | Sổ nợ tổng, Ghi nhanh, Ghi trả, Sổ riêng, kiểu D, Cấn trừ | 1 | 0,9 (19–21/11 thử trên Staging đạt S3 11/11 ca, đồng bộ D-1..D-4; sửa lỗi 1, 3, 4 (21/11, chưa push); trên `so-no-moi`: Sổ riêng, Ghi nhanh + cài đặt máy chủ, chọn người, Theo người, chi tiết người, Các đợt trước, Ghi trả; 13–15/11 thêm Lịch sử giao dịch + hủy, hàng chờ bền khi mất mạng, khóa giữa tab; Cấn trừ và gộp nơi để sau chuyến; chưa gộp `main`, chưa thử Supabase thật) |
| 23–29/11 | Báo nợ, trang xem sổ, Chia bill | 1 | 0,75 (S3b thử Staging đạt B-1..B-8, sửa lỗi 7 (21/11, chưa push); Chia bill xong cả Ghi nợ vào Sổ riêng (S3b); Báo nợ đã lên `so-no-moi` 18/11 (3c27d1a), máy thật R2, R7, R9 đạt với dữ liệu giả, QR chốt 18/11; chưa thử dữ liệu thật trên Staging; trang xem sổ để sau chuyến (Q6)) |
| 30/11–6/12 | Thống kê, Tôi, Quyền riêng tư, CSV, mất mạng/gửi lỗi/sửa trùng, trang chủ + Chính sách quyền riêng tư (Google Publish) | 1 | 0,1 (S2 trang chủ + Chính sách xong giao diện 16/11 trên bản xem trước; nội dung chưa công bố: chờ email thật, kiểm Data Access) |
| Chen ngang 16–17/11 | Sửa Auth P0 (A1–A3, Q12 khoản cần xử lý): rà soát, phương án, bản vẽ, lõi thuần | 0,5 | 0,15 (đặc tả + bản vẽ Q12 xong; `authGate.js` + `quarantine.js` thuần 29 bài kiểm, nhánh `auth-p0-logic` chưa push; nối vào app + thử thật sau 29/11) |
| 7–13/12 | Thử kín cả nhóm, sửa lỗi | 1 | 0 |
| 14–20/12 | Tổng kết chuyến, xóa chuyến dọn hình | 1 | 0 |
| 21–28/12 | Sửa lỗi, hướng dẫn cài, tạo chuyến Đà Lạt thật | 1 | 0 |
| **Tổng** | | **11,5** | **6,85 = 60%** |

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

## Bản mới nhất (23/11/2026)
**60%** (thiết kế 100%, code 51%) · thời gian đã qua 54% · **sớm khoảng 4 ngày** (giảm 3 ngày: 21–23/11 không thêm gói code mới, chỉ thử và sửa lỗi).

Đã xong (20/11 → 23/11):
- Thử S3, S3b, đồng bộ hai máy trên Staging với dữ liệu giả: **22/23 ca đạt** (S3-1..11, B-1..B-8, D-1..D-4); D-5 hoãn tới sau Auth P0. Không có yêu cầu hay dữ liệu mới nào trên Production.
- Thử thấy 7 chỗ, đã sửa 4 trên `so-no-moi` (21/11, 5 commit, **chỉ trên máy, chưa push**):
  - lỗi 7: Chia bill đổi số tiền thì hỏi "Bỏ liên kết Chia bill?" (`18c912f`)
  - lỗi 3: nợ hai chiều không còn hiện là "đã trả", chỉnh thêm theo góp ý của anh (`8128fdb`, `4b7650c`)
  - lỗi 4: ô ngày luôn dd/mm/yyyy trên laptop tiếng Anh (`b8bc671`)
  - lỗi 1: nhắc "Sổ đang lưu bằng khách" sai trên máy có phiên của dự án khác (`397c206`)
- Kiểm: `npm test` 201/201 đạt, build đạt, kiểm giao diện 360/412px không lỗi.
- Lỗi 5 (màu avatar Hùng khác giữa hai máy): đã tìm ra nguyên nhân là Chia bill và tờ ghi bill tô theo thứ tự trong bill, Sổ nợ tô theo thứ tự Sổ riêng. Có hướng sửa, chờ anh duyệt.
- Còn ghi lại, chưa sửa: lỗi 2 (Xấp hình hiện ngày 2 lần, màn A–E, sau 29/11), lỗi 6 (dữ liệu thử trước 19/11 nằm trên Production).

Đang làm:
| Việc | Xong | Còn |
|---|---|---|
| Sửa lỗi sau thử Staging | 4/5 lỗi màn mới | anh duyệt push, thử lại trên bản xem trước Staging; lỗi 5 chờ duyệt |
| S5 Thống kê → S6 Tôi | 0% | tới 29/11 |
| Gói Auth P0 (A1–A3 + Q12) | ~30% | nối vào app, thử thật: sau 29/11 |
| S2 Chính sách quyền riêng tư | ~70% | email liên hệ thật, đối chiếu Data Access, công bố |
| Chia theo món trong nhóm | ~20% | code từ 30/11 |
| UX Research A–E (anh) | anh giữ | đợt thử tới 28/11, chốt 29/11 |

Tiếp theo:
- Claude:
  1. Push 5 commit sửa lỗi khi anh duyệt, rồi theo dõi anh thử lại lỗi 1, 3, 4, 7 trên Staging (Opus).
  2. Lỗi 5 khi anh duyệt (Sonnet).
  3. S5 Thống kê rồi S6 Tôi, hạn 29/11 (Sonnet).
  4. Từ 30/11: gộp `so-no-moi` (Opus review A–E, migration Prod riêng), nối Auth P0, Chia theo món nhóm, lỗi (e)(f), lỗi 2, hardening.
- Anh:
  - Duyệt push 5 commit `done-nha` và 3 commit tài liệu `so-no`.
  - Duyệt hướng sửa lỗi 5 (cho em biết hai máy lúc đó đang ở màn nào).
  - Thử lại lỗi 1 và lỗi 4 trên laptop.
  - Đợt thử A–E; email cho Chính sách; quét VietQR Góp quỹ/Cân đối.

Trễ:
- Claude: không có việc trễ theo hạn. Tuần 16–22/11 còn 0,1 là Cấn trừ và gộp nơi, đã dời sau chuyến theo chốt Q4/Q5.
- Anh: duyệt bàn giao Lịch và Vào nhóm, trễ 29 ngày (đề xuất đóng).

Đang chờ anh:
- Duyệt push và lỗi 5 (từ 21/11)
- Quét VietQR Góp quỹ/Cân đối (từ 4/11)
- Thử Góp quỹ/Cân đối trên máy thật (từ 29/10)
- Ô ngày trên iPhone (từ 29/10)

Rủi ro:
| Việc | Cần trước | Vì sao |
|---|---|---|
| S5 Thống kê, S6 Tôi | 29/11 | Chưa bắt đầu, còn 6 ngày; trôi sang 30/11 thì chồng lên tuần đã quá tải |
| Tuần 30/11–6/12 quá tải | 6/12 | Gộp `so-no-moi`, sửa A–E sau nghiên cứu, Auth, Chia theo món, lỗi (e)(f), hardening |
| 5 commit sửa lỗi chưa push | trước gộp 30/11 | Chưa thử lại trên Staging thì chưa biết lỗi 1 (phiên thật) đã hết |
| Gộp `so-no-moi` vào `main` | 30/11 | Prod cần migration riêng: sao lưu, ghi lịch sử, đối chiếu, duyệt riêng |
| Auth thật (mức 2, iPhone) | 7/12 | Chưa thử iPhone thì không phát hành |
| Trang chủ + Chính sách công bố | 7/12 | Google Publish |
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
