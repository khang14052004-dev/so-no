# Bàn giao phiên (đọc đầu tiên khi đổi model hoặc mở phiên mới)

Cập nhật: 26/10/2026 11:00. Người viết: Claude (Opus). Cuối mỗi phiên, viết đè file này cho phiên sau.

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
| Bảng thiết kế | Artifact Design "Done Nha – Thiết kế (gộp Sổ nợ)", bản 224. Tìm bằng Artifact list, KHÔNG ghi link vào repo |
| Token | Artifact Design System "Done Nha" (48 màu) |
| Script vẽ bảng | `dn-tools.zip` (bản 224) ở `So-no/done-nha-workspace/08-tools/` trên máy anh; cách chạy trong README của gói |
| Thư mục làm việc | `So-no/done-nha-workspace/` trên máy anh (máy đã liên kết với phiên); đọc `00-START-HERE.md` |
Phiên mới trên đám mây có thể chưa có repo: dùng add_repo rồi clone; máy anh có thể chưa liên kết thì hỏi anh.

## 3. Trạng thái hiện tại (26/10)
- Pha 1 thiết kế gần xong: canvas bản 224 (115 bảng tĩnh + bảng so sánh icon), Design System bản 29. Mọi câu hỏi giao diện trong `docs/ke-hoach-tuan.md` đã chốt, trừ 3 token mới và màu avatar.
- Supabase: schema (commit 0df29e7) đã chạy trên dự án thật 26/10, đủ 8 bảng + bucket `receipts`. Bản mới (commit 821fc77, thêm 2 hàm Vào nhóm) chưa dán. Chưa bật Anonymous sign-ins, Allow manual linking. Gói Free tự tạm dừng sau 7 ngày ít hoạt động (thư cảnh báo 26/10): không mất dữ liệu, bật lại trong dashboard.
- Bàn giao (`done-nha-workspace/07-handoff/`): Lịch nhóm/chuyến (nháp, đã thêm 2 trạng thái), Vào nhóm (nháp 26/10, 4 câu chờ anh ở mục 10, có 8 chỗ lệch giữa bảng vẽ và máy chủ ở mục 6).
- Code app: chưa bắt đầu. Pha 2 (khung PWA, đăng nhập, vào nhóm) là việc kế tiếp, nên dùng Opus.

## 4. Đang dở
- **Vào nhóm:** anh đồng ý cả 4 câu (26/10). Bảng vẽ đã sửa (canvas 223: thẻ mời trước, tự thêm tên có hỏi trùng, Đổi link mời, bỏ link khôi phục). Máy chủ có `invite_card` (anon xem được) và `rotate_join_code` (chủ nhóm), commit 821fc77, 142 kiểm tra SQL; anh cần dán lại `schema.sql`. Anh ok thêm 3 chỗ nhỏ ở mục 6 (bỏ dòng tiền dưới tên, Giữ chỗ cho người tạo nhóm, nút Đăng nhập Google trên thẻ mời), canvas 224. Bàn giao đã chốt hết câu hỏi; việc kế tiếp là dựng khung app (Opus).
- **Token chờ duyệt:** `toast-bg`, `pink-wash`/`pink-ink`, `bubble-bg`/`bubble-edge`/`bubble-ink`; màu avatar (gradient hay 1 màu, gán cố định theo người). Danh sách: `05-tokens/khoang-trong-v208.md`.
- **Lịch sử giao dịch ở Sổ nợ tổng:** giữ nguyên, anh sẽ chỉnh vị trí sau.
- **Cờ "có thể thiếu dòng"** ở Các đợt trước: để sau chuyến.
- Bảng `DN-Icon-Phosphor` là bản so sánh cũ (cột "đang dùng" ghi canvas 214), không cập nhật theo icon Cân đối mới.

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
