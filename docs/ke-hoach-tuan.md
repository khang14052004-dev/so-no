# Kế hoạch theo tuần tới 28/12/2026

Lập 24/10/2026. **Đề xuất, anh duyệt.** Kế hoạch tổng nằm ở tài liệu claude.ai "Done Nha – kế hoạch đến tháng 1/2027"; file này là việc cụ thể theo tuần.
Xong việc nào thì đánh dấu [x] và ghi ngày. Đổi thứ tự thì ghi lý do một dòng.

Mốc cứng: pha 1 thiết kế xong **25/10** · pha 2 từ **26/10** · ngừng thêm tính năng **20/12** · app sẵn sàng **28/12** · đi Đà Lạt tối **2/1/2027**.

Cột "Model": gợi ý để đỡ tốn token. Opus cho việc khó, dễ sai đắt (tiền, SQL, bảo mật, giao diện kiểu mới); Sonnet cho việc theo khuôn đã có.

## Pha 1 – thiết kế (tới 25/10)

| | Việc | Ai | Model |
|---|---|---|---|
| [ ] | Anh duyệt bàn giao Lịch (`07-handoff/lich-nhom-chuyen.md`) | Anh | – |
| [x] | Anh trả lời 3 câu hỏi Xấp ảnh (`docs/de-xuat-xap-anh.md`) | Anh | – |
| [x] | Vẽ Xấp ảnh cho chuyến trên bảng bấm thử + 4 bảng tĩnh (canvas 211); thêm `PhotoStack` vào Design System (bản 20) | Claude | Opus (kiểu mới) |
| [x] | Bảng thử icon Phosphor (phương án C) trên canvas 212 | Claude | Sonnet |
| [x] | Anh chọn nét Regular (24/10) | Anh | – |
| [x] | Thay icon sang Phosphor Regular ở bảng bấm thử + Design System, chụp lại 104 bảng (canvas 213, DS 21) | Claude | Sonnet |
| [x] | Vẽ riêng Sổ nợ + Chia bill (bo tròn, Chia bill có dấu %), chụp lại 104 bảng (canvas 214, DS 22) | Claude | Sonnet |
| [x] | Xấp hình vẽ riêng, nút đổi kiểu xem chỉ icon, đổi chữ "ảnh" → "hình" (canvas 216, DS 23) | Claude | Sonnet |
| [x] | Sổ nợ + Chia bill chỉnh thành hình chữ nhật đứng như bảng cũ, chụp lại 104 bảng (canvas 217, DS 24) | Claude | Sonnet |
| [x] | Thẻ đầu Lịch chuyến thu gọn còn tổng tiền, nhãn "Cái hậu quả của nhóm"; xếp lại canvas (canvas 218, DS 25) | Claude | Sonnet |
| [ ] | Anh nói có thu gọn thẻ đầu Lịch Cơm trưa giống chuyến không | Anh | – |
| [ ] | Anh duyệt Cân đối dùng cán cân `scales` (hiện giữ vẽ tay, giống Cấn trừ; hai icon không nằm chung màn) | Anh | – |
| [ ] | Canvas kế tiếp: sửa màu lệch DS (`05-tokens/khoang-trong-v208.md`), vẽ 2 trạng thái Lịch còn thiếu, gửi lại `dn-tools.zip` | Claude | Sonnet |
| [ ] | Bàn giao màn Vào nhóm bằng link (iPhone tách bộ nhớ, trình duyệt Zalo) | Claude | Opus |

Nếu Xấp ảnh chưa xong 25/10 thì dời sang tuần 26/10, không chặn pha 2 (Xấp chỉ đổi cách hiện, dữ liệu đã đủ).

## Pha 2 – nền tảng và các màn

| Tuần | Việc | Model |
|---|---|---|
| 26/10–1/11 | Anh dán `schema.sql`, bật Allow manual linking. Claude kiểm schema trên Supabase thật. Chọn chỗ chạy (Cloudflare Pages hoặc Netlify), dựng khung app PWA, `tokens.css` sinh từ Design System, luật `.claude/rules/ui.md`. Đăng nhập khách + Google, "Giữ chỗ của bạn", link mời (Zalo, iPhone). | Opus |
| 2–8/11 | Nhóm/chuyến: tạo, mời, vào nhóm. Lịch + Xấp ảnh. Thêm khoản chi (chia đều), ảnh (nén ~200 KB + ảnh nhỏ ~15 KB, tải lên, `add_photo`). Ghi trên máy trước, đồng bộ sau. | Opus |
| 9–15/11 | Góp quỹ + thủ quỹ xác nhận; Số dư; Cân đối + Khóa; VietQR. | Opus |
| 16–22/11 | Sổ nợ tổng, Ghi nhanh, Ghi trả, Sổ riêng, kiểu D, Cấn trừ. | Sonnet (theo bàn giao), Opus khi đụng tính tiền |
| 23–29/11 | Báo nợ (tin nhắn, mã QR), trang xem sổ qua link, Chia bill (chia đều, theo món). | Sonnet |
| 30/11–6/12 | Thống kê, Tôi, Quyền riêng tư và dữ liệu, xuất CSV, mất mạng / gửi lỗi / sửa trùng. | Sonnet |
| 7–13/12 | Thử kín với cả nhóm trên iPhone thật (thêm vào màn hình chính, Zalo); sửa lỗi. | Opus cho lỗi khó |
| 14–20/12 | Tổng kết chuyến (ảnh chia sẻ) nếu kịp; hàm xóa chuyến dọn ảnh (Edge Function). **20/12 ngừng thêm tính năng.** | Opus |
| 21–28/12 | Chỉ sửa lỗi. Hướng dẫn nhóm cài app, tạo chuyến Đà Lạt thật, đặt ngày đi/về. **28/12 sẵn sàng.** | Sonnet |

## Mỗi màn làm theo vòng
Bàn giao (`07-handoff/<man>.md`) → code trong repo `done-nha` → `npm test` + `bash supabase/test/run.sh` → chụp 412px so với bảng `DN-*` → ghi `_progress.md`.

## Còn chờ anh chốt (không chặn)
Mức góp quỹ · màu chủ đạo và biểu tượng app · cách đo thành công trong brief · token màu loại khoản (`cat-*`).
