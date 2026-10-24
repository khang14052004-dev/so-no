# Bàn giao phiên (đọc đầu tiên khi đổi model hoặc mở phiên mới)

Cập nhật: 24/10/2026 10:40. Người viết: Claude (Opus). Cuối mỗi phiên, viết đè file này cho phiên sau.

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
| Bảng thiết kế | Artifact Design "Done Nha – Thiết kế (gộp Sổ nợ)", bản 212. Tìm bằng Artifact list, KHÔNG ghi link vào repo |
| Token | Artifact Design System "Done Nha" (48 màu) |
| Script vẽ bảng | `dn-tools.zip` (bản 212) ở `So-no/done-nha-workspace/08-tools/` trên máy anh; cách chạy trong README của gói |
| Thư mục làm việc | `So-no/done-nha-workspace/` trên máy anh (máy đã liên kết với phiên); đọc `00-START-HERE.md` |
Phiên mới trên đám mây có thể chưa có repo: dùng add_repo rồi clone; máy anh có thể chưa liên kết thì hỏi anh.

## 3. Trạng thái hiện tại (24/10)
- Pha 1 thiết kế: canvas bản 211 (104 bảng). Lịch nhóm dài hạn: lưới tháng. Chuyến: Xấp ảnh theo ngày (mặc định) + nút đổi Lịch tháng, bảng phác Tổng kết chuyến. Design System có PhotoStack (bản 20).
- Design System: thêm màu Lịch `cal-*` (24/10).
- Schema `done-nha` (commit 0df29e7): ngày đi/về, `group_calendar`, `group_spend_totals`, bảng ảnh riêng `entry_photos` (`add_photo`, `remove_photo`, `move_photos`). 125 kiểm tra SQL + 30 test lõi + 40 chuyến ngẫu nhiên đều qua. CHƯA chạy trên Supabase thật (anh dán ngày 26/10).
- Thư mục làm việc trên máy anh đã sắp xong.
- Bàn giao màn đầu tiên: Lịch (nháp, chờ anh duyệt).

## 4. Đang dở
- **Xấp ảnh cho chuyến:** đã vẽ bản đầu (canvas 211), chờ anh xem và góp ý. Chốt ở `docs/de-xuat-xap-anh.md`. Còn mở: token màu loại khoản (`cat-*`).
- **Icon (phương án C):** bảng thử `DN-Icon-Phosphor` đã đăng (canvas 212). Chờ anh chọn nét Regular hay Bold (và duyệt Cân đối dùng cán cân), rồi mới thay icon ở `gen_proto.py`/`proto_screens.py` (dict `I`, `tab()`, `_on`) và Design System, chụp lại 104 bảng.
- Canvas 213: sửa màu lệch DS (`05-tokens/khoang-trong-v208.md`), 2 trạng thái Lịch còn thiếu. Bàn giao Vào nhóm.

## 5. Luật hay vấp
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
