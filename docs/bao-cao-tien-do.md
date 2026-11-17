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

| Tuần | Gói việc | Trọng số | Xong 17/11 |
|---|---|---|---|
| Pha 1 | Thiết kế: canvas, Design System, bàn giao | 2 | 2 |
| 26/10–1/11 | Khung app, đăng nhập khách + Google, Giữ chỗ, thẻ mời + Zalo | 1 | 1 |
| 2–8/11 | Tạo nhóm, mời, vào nhóm, Lịch, Xấp hình, khoản chi | 0,6 | 0,6 |
| 2–8/11 | Hình hóa đơn (chụp, nén, tải lên, xem, xóa) | 0,25 | 0,25 (xong 2/11, anh thử máy thật đạt) |
| 2–8/11 | Ghi khi mất mạng, đồng bộ sau | 0,15 | 0,15 (xong 3/11, anh thử S24 đạt) |
| 9–15/11 | Góp quỹ, Số dư, Quỹ, Cân đối, Khóa | 0,6 | 0,6 (chờ thử máy thật) |
| 9–15/11 | Tài khoản nhận tiền + VietQR | 0,4 | 0,4 (code xong 4/11; schema đã có trên Supabase 11/11; chờ quét thử app ngân hàng thật) |
| 16–22/11 | Sổ nợ tổng, Ghi nhanh, Ghi trả, Sổ riêng, kiểu D, Cấn trừ | 1 | 0,85 (trên `so-no-moi`: Sổ riêng, Ghi nhanh + cài đặt máy chủ, chọn người, Theo người, chi tiết người, Các đợt trước, Ghi trả; 13–15/11 thêm Lịch sử giao dịch + hủy, hàng chờ bền khi mất mạng, khóa giữa tab; Cấn trừ và gộp nơi để sau chuyến; chưa gộp `main`, chưa thử Supabase thật) |
| 23–29/11 | Báo nợ, trang xem sổ, Chia bill | 1 | 0,35 (Chia bill xong cả nút Ghi nợ vào Sổ riêng (S3b, 13–15/11); Báo nợ chưa làm; trang xem sổ để sau chuyến (Q6)) |
| 30/11–6/12 | Thống kê, Tôi, Quyền riêng tư, CSV, mất mạng/gửi lỗi/sửa trùng, trang chủ + Chính sách quyền riêng tư (Google Publish) | 1 | 0,1 (S2 trang chủ + Chính sách xong giao diện 16/11 trên bản xem trước; nội dung chưa công bố: chờ email thật, kiểm Data Access) |
| Chen ngang 16–17/11 | Sửa Auth P0 (A1–A3, Q12 khoản cần xử lý): rà soát, phương án, bản vẽ, lõi thuần | 0,5 | 0,15 (đặc tả + bản vẽ Q12 xong; `authGate.js` + `quarantine.js` thuần 29 bài kiểm, nhánh `auth-p0-logic` chưa push; nối vào app + thử thật sau 29/11) |
| 7–13/12 | Thử kín cả nhóm, sửa lỗi | 1 | 0 |
| 14–20/12 | Tổng kết chuyến, xóa chuyến dọn hình | 1 | 0 |
| 21–28/12 | Sửa lỗi, hướng dẫn cài, tạo chuyến Đà Lạt thật | 1 | 0 |
| **Tổng** | | **11,5** | **6,4 = 56%** |

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

## Bản mới nhất (17/11/2026)
**56%** (thiết kế 100%, code 46%) · thời gian đã qua 46% · **sớm khoảng 7 ngày** (15/11 sớm ~9 ngày; 16–17/11 dồn vào việc chen ngang Auth P0, thêm 0,5 phần vào tổng).

Đã xong (15/11 → 17/11):
- S2 trang Giới thiệu + Chính sách quyền riêng tư trên bản xem trước (`done-nha` 9764e0d); anh duyệt giao diện, nội dung chưa công bố.
- Google OAuth: giữ Testing, chưa mua tên miền riêng cho Supabase; Redirect URL bản xem trước anh tự thêm.
- Đặc tả Chia theo món trong nhóm (cột `detail` phương án A, luật đồng lẻ, bảng ca kiểm); chưa code.
- Chen ngang: rà soát đăng nhập + giữ dữ liệu mức 1 (4 lỗi P0), phương án A1–A3 + phụ lục 1–2, câu chữ T1–T13 và H1–H16, bản vẽ Q12 "Khoản cần xử lý" 11 khung, 38 ca nghiệm thu; lõi thuần `authGate.js` + `quarantine.js` (29 bài kiểm, thử 11 đột biến đều bị bắt; nhánh `auth-p0-logic` chưa push, patch ở `07-handoff`).

Đang làm:
| Việc | Xong | Còn |
|---|---|---|
| Gói Auth P0 (A1–A3 + Q12) | ~30% | nối vào app, giao diện Q12, thử thật mức 2 + iPhone: sau 29/11 |
| S2 Chính sách quyền riêng tư | ~70% | email liên hệ thật, đối chiếu Data Access, công bố |
| Chia theo món trong nhóm | ~20% | code từ 30/11 |
| S4 Báo nợ → S5 Thống kê → S6 Tôi | 0% | bị lùi vì việc chen ngang |
| UX Research A–E (anh) | anh giữ | đợt thử 16–28/11, chốt 29/11 |

Đã quyết dời gần đây:
| Việc | Dời tới | Quyết |
|---|---|---|
| Nối Auth A1–A3 + giao diện Q12 + thử thật | 30/11–6/12 | 16–17/11 |
| Lỗi A–E (e) trả dư, (f) hai máy ghi trùng | sau 29/11 (trong đợt thử dặn người thử tránh) | 16/11 |
| Chia theo món trong nhóm (code) | từ 30/11 | 16/11 |
| Thanh nhắc cài app | sau 29/11, chờ Auth an toàn | 16/11 |
| Xóa/Hủy rà A–E (h), (i) | sau 29/11 | 16/11 |
| Mức 2 OAuth (Gmail thử) | chưa duyệt; cần trước thử kín | 16/11 |
| Tên miền riêng cho Supabase Auth | khi mở dùng rộng | 16/11 |
| Quét bill tự điền | chờ anh nói | 13/11 |
| PA-2 làm tròn góp quỹ, Cấn trừ, gộp nơi, link xem sổ | sau chuyến | 9–10/11 |

Tiếp theo:
- Claude: S4 Báo nợ → S5 Thống kê → S6 Tôi trên `so-no-moi` tới 29/11; từ 30/11: gộp `so-no-moi` (Opus review A–E), nối Auth, Chia theo món nhóm, lỗi (e)(f).
- Anh: đợt thử 16–28/11; duyệt 3 câu Q12 (H7c, H16, "Thôi"); email liên hệ cho Chính sách; quyết mức 2 (Gmail thử).

Trễ: Claude không có việc trễ theo hạn; S4–S6 lùi ~2 ngày so với thứ tự dự kiến vì Auth chen ngang (hạn tuần vẫn 29/11). Anh: duyệt bàn giao Lịch và Vào nhóm (trễ 23 ngày so với pha 1, đề xuất đóng). Đang chờ anh: quét VietQR app ngân hàng thật (từ 4/11), thử Góp quỹ/Cân đối máy thật (từ 29/10), ô ngày iPhone (từ 29/10), thử Sổ riêng + S3b với Supabase thật (từ 12/11).

Rủi ro:
| Việc | Cần trước | Vì sao |
|---|---|---|
| Tuần 30/11–6/12 quá tải | 6/12 | Dồn: gộp `so-no-moi`, thay đổi A–E sau nghiên cứu, nối Auth + thử thật, Chia theo món nhóm, lỗi (e)(f), còn S5–S6 nếu chưa xong |
| Auth P0 thử thật (mức 2, iPhone N13) | 7/12 | Chưa duyệt Gmail thử; iPhone chưa thử thì không phát hành |
| Trang chủ + Chính sách công bố | 7/12 | Google Publish |
| Gộp `so-no-moi` vào `main` | 30/11 | Đổi schema, phải dán lại |
| Supabase Free tự ngủ | 28/12 | Giữ hoạt động hoặc lên Pro |
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
