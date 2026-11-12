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

| Tuần | Gói việc | Trọng số | Xong 12/11 |
|---|---|---|---|
| Pha 1 | Thiết kế: canvas, Design System, bàn giao | 2 | 2 |
| 26/10–1/11 | Khung app, đăng nhập khách + Google, Giữ chỗ, thẻ mời + Zalo | 1 | 1 |
| 2–8/11 | Tạo nhóm, mời, vào nhóm, Lịch, Xấp hình, khoản chi | 0,6 | 0,6 |
| 2–8/11 | Hình hóa đơn (chụp, nén, tải lên, xem, xóa) | 0,25 | 0,25 (xong 2/11, anh thử máy thật đạt) |
| 2–8/11 | Ghi khi mất mạng, đồng bộ sau | 0,15 | 0,15 (xong 3/11, anh thử S24 đạt) |
| 9–15/11 | Góp quỹ, Số dư, Quỹ, Cân đối, Khóa | 0,6 | 0,6 (chờ thử máy thật) |
| 9–15/11 | Tài khoản nhận tiền + VietQR | 0,4 | 0,4 (code xong 4/11; schema đã có trên Supabase 11/11; chờ quét thử app ngân hàng thật) |
| 16–22/11 | Sổ nợ tổng, Ghi nhanh, Ghi trả, Sổ riêng, kiểu D, Cấn trừ | 1 | 0,7 (code xong trên nhánh `so-no-moi` 11–12/11: Sổ riêng, Ghi nhanh + cài đặt lưu máy chủ, chọn người, Theo người, chi tiết người, Các đợt trước, Ghi trả; anh đã xem bản xem trước trên S24; Cấn trừ và gộp nơi để sau chuyến; chưa gộp `main`) |
| 23–29/11 | Báo nợ, trang xem sổ, Chia bill | 1 | 0,25 (S1 Chia bill: tính tiền xong, UI anh chốt 11/11 14:28 gồm tờ bill gửi hình; nút Ghi nợ chưa nối Sổ riêng (S3b); Báo nợ, trang xem sổ chưa làm) |
| 30/11–6/12 | Thống kê, Tôi, Quyền riêng tư, CSV, mất mạng/gửi lỗi/sửa trùng, trang chủ + Chính sách quyền riêng tư (Google Publish) | 1 | 0 |
| 7–13/12 | Thử kín cả nhóm, sửa lỗi | 1 | 0 |
| 14–20/12 | Tổng kết chuyến, xóa chuyến dọn hình | 1 | 0 |
| 21–28/12 | Sửa lỗi, hướng dẫn cài, tạo chuyến Đà Lạt thật | 1 | 0 |
| **Tổng** | | **11** | **5,9 = 54%** |

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

## Bản mới nhất (12/11/2026)
**54%** (thiết kế 100%, code 43%) · thời gian đã qua 39% · **sớm khoảng 11 ngày** (11/11 sớm ~6 ngày; S3 Sổ riêng và Chia bill UI làm xong sớm hơn kế hoạch 16–29/11, nhưng nằm trên nhánh `so-no-moi`, chưa gộp `main`).

Đã xong (11/11 → 12/11):
- S3 Sổ riêng trên `so-no-moi`: máy chủ thêm `ensure_personal`, `add_personal_member`, `rename_personal_member`, `remove_personal_member`, bảng `user_settings`; màn `/so-no` (Đang cho nợ, Ghi nhanh, Theo người, chi tiết người, Các đợt trước, Ghi trả nhanh).
- Cài đặt Ghi nhanh lưu trên máy chủ (chip nhóm, chip số tiền, thứ tự hiển thị).
- Chọn người dùng chung (PersonPicker + QuickPeople): tên phân biệt dấu, ghim, đổi tên, xóa khỏi sổ, nút back đóng popup trước; Chia bill giữ nguyên.
- Chia bill: UI chốt 11/11 14:28 (tờ bill, Gửi hình, một món nhiều người, bill giữ khi tải lại).
- Rà UI Sổ nợ 12/11: bỏ khối nổi trong bảng đáy; chuẩn hóa chữ Cài đặt Ghi nhanh và nhịp khoảng cách (28/8/16); thẻ Đang cho nợ hiện số đầy đủ. Chia bill đối chiếu pixel: không đổi.
- Kiểm: 96 bài JS, kiểm SQL qua; build qua.

Tiếp theo:
- Claude: S3b nối nút Ghi nợ của Chia bill với Sổ riêng → S2 Chính sách (hạn 7/12) → S4 Báo nợ → S5 Thống kê → S6 Tôi (Sonnet, mỗi phiên một việc). Opus: review chỗ chạm A–E trước khi gộp `main` 30/11; sửa lỗi A–E nếu anh duyệt.
- Anh: thử `so-no-moi.done-nha.pages.dev` trên máy thật (bàn phím mở, iPhone); dán lại `schema.sql` mới của nhánh `so-no-moi` nếu chưa; P1 đánh giá chuyên gia (10–15/11), chuẩn bị thử 5 người (16–22/11); quyết có sửa lỗi (e), (f) trên `main` trước 16/11 không; quét thử VietQR app ngân hàng thật.

Trễ: Claude không có việc trễ. Anh trễ so với hạn pha 1 (25/10): duyệt bàn giao Lịch và Vào nhóm (18 ngày; hai màn đã code và thử đạt, đề xuất đóng). Đang chờ anh: quét VietQR app ngân hàng thật (từ 4/11), thử Góp quỹ/Cân đối máy thật (từ 29/10), ô ngày iPhone (từ 29/10), bạn iPhone thử (từ 28/10), thử Theo món S1 (từ 9/11), thử Sổ riêng với bàn phím mở trên máy thật (từ 12/11).

Rủi ro:
| Việc | Cần trước | Vì sao |
|---|---|---|
| Lỗi A–E (e) trả dư mất, (f) hai máy ghi trùng | 16/11 | Đợt thử người dùng thật chạy trên `main`; dễ gặp khi hai người cùng bấm |
| Gộp `so-no-moi` vào `main` | 30/11 | Anh kiểm bản xem trước + Opus review chỗ chạm A–E; có đổi schema (Sổ riêng, cài đặt, xóa người) nên phải dán lại |
| S3b Ghi nợ Chia bill | ~25/11 | Chia bill hiện chưa ghi vào sổ |
| Camera + gửi hình trên iPhone thật | 7/12 | Chưa thử |
| Trang chủ + Chính sách quyền riêng tư (S2) | 7/12 | Google Publish |
| Màu chủ đạo | ~30/11 | Biểu tượng đã chốt 3/11; màu còn mở |
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
