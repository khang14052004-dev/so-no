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

| Tuần | Gói việc | Trọng số | Xong 15/11 |
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
| 30/11–6/12 | Thống kê, Tôi, Quyền riêng tư, CSV, mất mạng/gửi lỗi/sửa trùng, trang chủ + Chính sách quyền riêng tư (Google Publish) | 1 | 0 |
| 7–13/12 | Thử kín cả nhóm, sửa lỗi | 1 | 0 |
| 14–20/12 | Tổng kết chuyến, xóa chuyến dọn hình | 1 | 0 |
| 21–28/12 | Sửa lỗi, hướng dẫn cài, tạo chuyến Đà Lạt thật | 1 | 0 |
| **Tổng** | | **11** | **6,15 = 56%** |

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

## Bản mới nhất (15/11/2026)
**56%** (thiết kế 100%, code 46%) · thời gian đã qua 43% · **sớm khoảng 9 ngày** (12/11 sớm ~11 ngày; 13–15/11 dồn vào làm hàng chờ Sổ riêng chắc chắn hơn kế hoạch, nên % tăng chậm hơn thời gian).

Đã xong (12/11 → 15/11):
- Chia bill Theo món làm tròn kiểu Grab, khớp đơn Grab thật từng đồng; ô "Phí áp dụng" chia đều; hỏi "Tên bạn trên bill" khi trùng.
- S3b: nút Ghi nợ của Chia bill ghi vào Sổ riêng (Chia đều qua Ghi nhanh có băng đếm người; Theo món ghi thẳng, khớp tên theo mã, hỏi tên gần giống).
- Sổ nợ: mỗi lần một nhóm, khóa ghi khi chưa đọc được sổ, mất mạng hai cấp, Lịch sử giao dịch + hủy có Hoàn tác (luật C1–C2).
- Hàng chờ bền một kho cho Ghi nhanh và Chia bill: tự gửi khi có mạng, lưu lý do bị từ chối (F2), bỏ khoản của người đã xóa (F3), khóa giữa các tab, báo tab bản cũ / "Đang xử lý ở tab khác", giữ cả hai bản khi lệch; chữ hàng chờ chuẩn hóa.
- Commit + push 15/11: `done-nha` `06ff834` (nhánh `so-no-moi`), `so-no` `57fcbe9`; Cloudflare build bản xem trước thành công. Không đổi schema.
- Kiểm: 176 bài JS, build qua; bấm thử giả lập v19, audit5–7, 9–11 đạt hết ở 360 và 412px. Script bấm thử đã chép về `08-tools/bam-thu-so-no`.

Tiếp theo:
- Claude: S2 Chính sách quyền riêng tư + trang chủ (hạn 7/12) → S4 Báo nợ → S5 Thống kê → S6 Tôi (Sonnet, mỗi phiên một việc). Opus: review chỗ chạm A–E trước khi gộp `main` 30/11.
- Anh: đợt thử 5 người trên `main` từ 16/11; thử `so-no-moi.done-nha.pages.dev` với Supabase thật (Ghi nợ từ Chia bill, mất mạng rồi có mạng, hai tab) khi rảnh (không bắt buộc trước 29/11); quét VietQR app ngân hàng thật.

Trễ: Claude không có việc trễ. Anh trễ so với hạn pha 1 (25/10): duyệt bàn giao Lịch và Vào nhóm (21 ngày; hai màn đã code và thử đạt, đề xuất đóng). Đang chờ anh: quét VietQR app ngân hàng thật (từ 4/11), thử Góp quỹ/Cân đối máy thật (từ 29/10), ô ngày iPhone (từ 29/10), bạn iPhone thử (từ 28/10), thử Sổ riêng + S3b với Supabase thật (từ 12/11).

Rủi ro:
| Việc | Cần trước | Vì sao |
|---|---|---|
| Lỗi A–E (e) trả dư mất, (f) hai máy ghi trùng | 16/11 (mai) | Đợt thử người dùng thật chạy trên `main`; chưa thấy anh quyết sửa hay không |
| Gộp `so-no-moi` vào `main` | 30/11 | Anh kiểm bản xem trước + Opus review A–E; có đổi schema (Sổ riêng, cài đặt, xóa người) nên phải dán lại |
| Hàng chờ Sổ riêng chưa thử thật | 30/11 | Mới thử giả lập; chưa thử Supabase thật, iPhone (app ở màn hình chính), trình duyệt không có `navigator.locks` |
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
| 15/11 | 56% | 100% | 46% | 43% | sớm ~9 ngày |
