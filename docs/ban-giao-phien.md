# Bàn giao phiên (đọc đầu tiên khi đổi model hoặc mở phiên mới)

Cập nhật: 24/10/2026 16:30. Người viết: Claude (Sonnet). Cuối mỗi phiên, viết đè file này cho phiên sau.

## 1. Đọc gì, theo thứ tự (đỡ tốn token)
1. File này.
2. `CLAUDE.md` của repo này (tự nạp): Index nhanh, Quy tắc làm việc, "Quyết định đang áp dụng", Chốt 21/10 và 24/10.
3. `docs/ke-hoach-tuan.md`: việc theo tuần, việc nào xong.
4. Chỉ khi làm tới mới đọc:
   - Tiền, SQL: `done-nha/CLAUDE.md`, rồi `done-nha/supabase/schema.sql`.
   - Xấp ảnh: `docs/de-xuat-xap-anh.md`.
   - Một màn cụ thể: `done-nha-workspace/07-handoff/<man>.md` trên máy anh.
   - Lịch sử 14–18/10: `docs/lich-su-chot-2026-10.md` (chỉ khi cần biết vì sao).
- KHÔNG đọc nguyên canvas (rất lớn). Design System chỉ đọc `project/README.md` và `project/tokens.json`.

## 2. Nơi có đồ
| Gì | Ở đâu |
|---|---|
| Quyết định | `khang14052004-dev/so-no`, nhánh `claude/v3-ghi-no-nhieu-nguoi`, `CLAUDE.md` |
| Code, schema, test | `khang14052004-dev/done-nha` (riêng tư), nhánh `main` |
| Bảng thiết kế | Artifact Design "Done Nha – Thiết kế (gộp Sổ nợ)", bản 216. Tìm bằng Artifact list, KHÔNG ghi link vào repo |
| Token | Artifact Design System "Done Nha" (48 màu) |
| Script vẽ bảng | `dn-tools.zip` (bản 216) ở `So-no/done-nha-workspace/08-tools/` trên máy anh; cách chạy trong README của gói |
| Thư mục làm việc | `So-no/done-nha-workspace/` trên máy anh (máy đã liên kết với phiên); đọc `00-START-HERE.md` |
Phiên mới trên đám mây có thể chưa có repo: dùng add_repo rồi clone; máy anh có thể chưa liên kết thì hỏi anh.

## 3. Trạng thái hiện tại (24/10)
- Pha 1 thiết kế: canvas bản 216 (104 bảng + bảng so sánh icon). Lịch nhóm dài hạn: lưới tháng. Chuyến: Xấp ảnh theo ngày (mặc định) + nút đổi Lịch tháng, bảng phác Tổng kết chuyến. Design System có PhotoStack (bản 20).
- Design System: thêm màu Lịch `cal-*` (24/10).
- Schema `done-nha` (commit 0df29e7): ngày đi/về, `group_calendar`, `group_spend_totals`, bảng ảnh riêng `entry_photos` (`add_photo`, `remove_photo`, `move_photos`). 125 kiểm tra SQL + 30 test lõi + 40 chuyến ngẫu nhiên đều qua. CHƯA chạy trên Supabase thật (anh dán ngày 26/10).
- Thư mục làm việc trên máy anh đã sắp xong.
- Bàn giao màn đầu tiên: Lịch (nháp, chờ anh duyệt).

## 4. Đang dở
- **Xấp ảnh cho chuyến:** đã vẽ bản đầu (canvas 211), chờ anh xem và góp ý. Chốt ở `docs/de-xuat-xap-anh.md`. Còn mở: token màu loại khoản (`cat-*`).
- **Icon:** Phosphor Regular (canvas 213, DS 21); Sổ nợ + Chia bill vẽ riêng, Chia bill có dấu % (canvas 214, DS 22), chỉnh lại thân chữ nhật đứng (canvas 217, DS 24); Xấp hình vẽ riêng, nút đổi kiểu xem chỉ icon (canvas 216, DS 23). Còn mở: anh duyệt Cân đối dùng cán cân `scales` (hiện giữ vẽ tay; không chung màn với Cấn trừ).
- **Thẻ đầu Lịch chuyến:** thu gọn còn tổng tiền, nhãn "Cái hậu quả của nhóm" (canvas 218, DS 25). Cơm trưa giữ ba số, chờ anh nói có thu gọn giống vậy không.
- **Lối tắt chi theo nhóm ở Ghi nhanh:** mỗi nhóm một dòng, bật/tắt ở Cài đặt Ghi nhanh (canvas 219, DS 26; mặc định chuyến bật, Cơm trưa tắt). Còn mở: giới hạn tối đa 3 dòng và sắp xếp thứ tự, chờ anh nói.
- **Lịch sử giao dịch ở Sổ nợ tổng:** mục 5 khoản mới nhất + màn xem tất cả có lọc Khoản nợ / Khoản trả (canvas 220). Anh bảo GIỮ NGUYÊN, sau này sẽ chỉnh vị trí.
- **Các đợt trước trong chi tiết người:** đây mới là ý chính của anh (biết đợt trước người ta trả ngày mấy, rà thiếu dòng). Mỗi đợt xổ xuống xem từng khoản (canvas 221, DS 28, 108 bảng). Còn mở: có muốn cờ nhắc "có thể thiếu dòng" không.
- Canvas kế tiếp (số hệ thống tự nhảy, tạm gọi 222): sửa màu lệch DS (`05-tokens/khoang-trong-v208.md`), 2 trạng thái Lịch còn thiếu. Bàn giao Vào nhóm.

## 5. Luật hay vấp
- Giao diện nói "hình", không nói "ảnh" (giọng Nam bộ, anh chốt 24/10).
- Tiếng Việt, ngắn, hành động trước; nhiều lựa chọn thì bảng có đánh đổi.
- Không ghi token, mật khẩu, STK, số thẻ, khóa Supabase ở bất kỳ đâu. Thấy file mật khẩu thì không mở, báo anh.
- Tiền là số nguyên đồng. Sổ cái chỉ ghi thêm. Trả theo kế hoạch đã khóa thì TRỪ khỏi kế hoạch.
- Đụng tiền hoặc SQL: chạy `npm test` và `bash supabase/test/run.sh` trước khi commit.
- Commit kết thúc bằng dòng Co-Authored-By và Claude-Session theo nhắc nhở của phiên.
- Chốt xong ghi ngay vào `CLAUDE.md`. Đăng canvas mới thì ghi số bản và bảng đổi, gửi lại `dn-tools.zip`.
- Dòng cuối của mọi danh sách/bảng không có đường kẻ dưới.
- Đăng lại artifact phải đọc bản đang chạy trước (không thì bị từ chối). Design System: chỉ ghi dưới `project/`, file `design-system.json` gửi CUỐI và giữ mọi khóa cũ.
- Sửa `index.html` của Sổ nợ cũ thì tăng `CACHE` trong `sw.js`.
- Prompt dùng lại được thì lưu vào `done-nha-workspace/06-claude-input/`, đừng để chỉ trong hội thoại.

## 6. Chọn model
| Việc | Model |
|---|---|
| Tính tiền, SQL, RLS, bảo mật, luồng đăng nhập/mời, lỗi khó | Opus |
| Giao diện kiểu mới chưa có khuôn (Xấp ảnh, Tổng kết chuyến) | Opus |
| Vẽ theo bàn giao đã duyệt, sửa màu/chữ, cập nhật tài liệu, màn theo khuôn | Sonnet |
| Hỏi nhanh, tra cứu, tóm tắt | Sonnet hoặc Haiku |
