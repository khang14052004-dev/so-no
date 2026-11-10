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

| Tuần | Gói việc | Trọng số | Xong 10/11 |
|---|---|---|---|
| Pha 1 | Thiết kế: canvas, Design System, bàn giao | 2 | 2 |
| 26/10–1/11 | Khung app, đăng nhập khách + Google, Giữ chỗ, thẻ mời + Zalo | 1 | 1 |
| 2–8/11 | Tạo nhóm, mời, vào nhóm, Lịch, Xấp hình, khoản chi | 0,6 | 0,6 |
| 2–8/11 | Hình hóa đơn (chụp, nén, tải lên, xem, xóa) | 0,25 | 0,25 (xong 2/11, anh thử máy thật đạt) |
| 2–8/11 | Ghi khi mất mạng, đồng bộ sau | 0,15 | 0,15 (xong 3/11, anh thử S24 đạt) |
| 9–15/11 | Góp quỹ, Số dư, Quỹ, Cân đối, Khóa | 0,6 | 0,6 (chờ thử máy thật) |
| 9–15/11 | Tài khoản nhận tiền + VietQR | 0,4 | 0,4 (code xong 4/11; chờ dán schema, quét thử app ngân hàng thật) |
| 16–22/11 | Sổ nợ tổng, Ghi nhanh, Ghi trả, Sổ riêng, kiểu D, Cấn trừ | 1 | 0 |
| 23–29/11 | Báo nợ, trang xem sổ, Chia bill | 1 | 0,1 (S1 Chia bill: giao diện xong trên nhánh `so-no-moi`, nút Ghi nợ chưa nối, chờ anh kiểm UX) |
| 30/11–6/12 | Thống kê, Tôi, Quyền riêng tư, CSV, mất mạng/gửi lỗi/sửa trùng, trang chủ + Chính sách quyền riêng tư (Google Publish) | 1 | 0 |
| 7–13/12 | Thử kín cả nhóm, sửa lỗi | 1 | 0 |
| 14–20/12 | Tổng kết chuyến, xóa chuyến dọn hình | 1 | 0 |
| 21–28/12 | Sửa lỗi, hướng dẫn cài, tạo chuyến Đà Lạt thật | 1 | 0 |
| **Tổng** | | **11** | **5,1 = 46%** |

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

## Bản mới nhất (10/11/2026)
**46%** (thiết kế 100%, code 34%) · thời gian đã qua 37% · **sớm khoảng 7 ngày** (2/11 sớm ~10 ngày; từ 3/11 phần lớn công sức vào nghiên cứu UX, phân tích và S1 nên % lên chậm hơn).

Đã xong (2/11 → 10/11):
- 3/11: ghi khoản chi khi mất mạng + xem bản lưu (anh thử S24 đạt); Xấp hình cho nhóm dài hạn (theo tháng/tuần, viên độ thân); xóa thành viên / tự rời nhóm; biểu tượng app chốt; chi tiết khoản có thẻ hình, sửa tên/ngày nhóm, biểu tượng nhóm, xóa nhóm.
- 4/11: hình đại diện nhóm (có khung cắt), màn đầu có dòng hoạt động in đậm + mở nhóm nhanh, Lịch tháng dạng danh sách phẳng, **Tài khoản nhận tiền + VietQR** (code xong, `done-nha` 7cd3260).
- 9/11: chốt kế hoạch UX Research A–E (bản 3); O1 phân tích kiến trúc xong, anh chốt Q1–Q7 (code 6 màn mới trên nhánh `so-no-moi`, không đụng `main` tới 30/11); kiểm Supabase chỉ đọc (thiếu 7cd3260).
- S1 Chia bill (nhánh `so-no-moi`, commit 215c366 + d85b724): Chia đều và Theo món khớp bảng thiết kế, 72 bài kiểm qua; nút Ghi nợ chưa nối tới S3b; quy tắc phân bổ lẻ anh chốt đã ghi vào CLAUDE.md.
- Phân tích làm tròn bill + phần dư vào quỹ (chỉ phân tích, chưa duyệt) đã lưu ở `07-handoff/2026-11-09-s1-lam-tron-quy-phan-tich.md` + sơ đồ.

Tiếp theo:
- Claude: chờ anh kiểm UX S1 (preview commit 215c366) và trả lời Q1–Q10 làm tròn; sau đó S2 Chính sách → S3 Sổ riêng → S3b → S4 Báo nợ → S5 Thống kê → S6 Tôi (Sonnet, mỗi phiên một việc); Opus review A–E trước khi gộp `main` 30/11.
- Anh: UX Research (P1: đánh giá chuyên gia 10–15/11, thử 5 người ngoài nhóm 16–22/11, chốt A–E 29/11); **dán `schema.sql` mới nhất vào Supabase trước 12/11**; kiểm UX S1; trả lời Q1–Q10.

Trễ: Claude không có việc trễ. Anh trễ so với hạn pha 1 (25/10): duyệt bàn giao Lịch và Vào nhóm (16 ngày; hai màn đã code và thử đạt, đề xuất đóng). Đang chờ anh: dán schema (từ 4/11, hạn cứng 12/11), quét thử VietQR bằng app ngân hàng thật (từ 4/11), thử Góp quỹ/Cân đối máy thật (từ 29/10), ô ngày iPhone (từ 29/10), bạn iPhone thử (từ 28/10).

Rủi ro:
| Việc | Cần trước | Vì sao |
|---|---|---|
| Dán `schema.sql` | 12/11 | Supabase thiếu 7cd3260; các hàm xóa thành viên, hình đại diện, tài khoản nhận tiền chưa chạy được |
| Quyết Q1–Q10 làm tròn | khi làm S3b (Ghi nợ) | Quyết định có thể cần đổi schema (loại dòng mới, bật quỹ), phải duyệt riêng |
| Camera + gửi hình trên iPhone thật | 7/12 | Chưa thử |
| Trang chủ + Chính sách quyền riêng tư (S2 đang tạm dừng) | 7/12 | Google Publish |
| Biểu tượng app, màu chủ đạo | ~30/11 | Biểu tượng đã chốt 3/11; màu chủ đạo còn mở |
| Supabase Free tự ngủ | 28/12 | Giữ hoạt động hoặc lên Pro |
| Pháp lý (chưa hỏi luật sư) | trước mở cho người ngoài nhóm bạn | Luật BVDLCN, STK |

## Lịch sử %
| Ngày | Tổng | Thiết kế | Code | Thời gian | Sớm/chậm |
|---|---|---|---|---|---|
| 30/10 | 38% | 100% | 24% | 22% | sớm ~12 ngày |
| 2/11 | 40% | 100% | 27% | 26% | sớm ~10 ngày |
| 10/11 | 46% | 100% | 34% | 37% | sớm ~7 ngày |
