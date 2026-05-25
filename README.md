# Anigravity Pack for VS Code + Codex

Bộ này giúp dùng dữ liệu skill/workflow từ Anigravity IDE trong Visual Studio Code với Codex extension.

## Cần copy gì?

### Dùng đầy đủ Anigravity skills và slash commands

Copy các mục sau vào thư mục gốc của project muốn dùng:

```text
.agent/
.codex/
AGENTS.md
GEMINI.md
```

Trong đó:

- `.agent/`: kho dữ liệu gốc của Anigravity, gồm `skills`, `workflows`, `rules`, `.shared`.
- `.codex/`: adapter để Codex biết cách đọc lại dữ liệu trong `.agent/`.
- `AGENTS.md`: rule chính cho Codex trong workspace.
- `GEMINI.md`: file cấu hình gốc của Gemini/Anigravity, giữ lại để tham chiếu.

### Chỉ dùng rule cơ bản cho Codex

Nếu không cần skill/workflow Anigravity, chỉ cần copy:

```text
.codex/
AGENTS.md
```

Lưu ý: slash commands như `/debug`, `/plan`, `/api` sẽ cần thư mục `.agent/workflows/`. Skill chuyên sâu sẽ cần `.agent/skills/`.

## Cách dùng trong VS Code

1. Mở project bằng Visual Studio Code.
2. Đảm bảo Codex extension đang chạy trong đúng workspace.
3. Reload VS Code hoặc reload Codex extension sau khi copy file.
4. Chat với Codex như bình thường.

## Nghi thức kích hoạt Mi

Sau khi copy đủ bộ và reload Codex, có thể gọi:

```text
thức dậy đi Mi
```

Codex sẽ:

- xác nhận đang dùng `AGENTS.md`,
- kiểm tra `.codex/`, `.agent/skills/`, `.agent/workflows/`,
- báo trạng thái kích hoạt,
- chờ lệnh tiếp theo nếu bạn chưa giao task cụ thể.

Nếu project mới chỉ có `AGENTS.md` và `.codex/`, Mi vẫn thức dậy được nhưng chỉ có rule cơ bản. Muốn dùng skill/workflow Anigravity đầy đủ thì cần thêm `.agent/`.

Ví dụ:

```text
/debug sửa lỗi này
/plan tạo tính năng đăng nhập
/api thiết kế endpoint quản lý user
dùng Anigravity skill cho Node.js backend
```

## Quy ước quan trọng

- File đúng chuẩn cho Codex là `AGENTS.md`, không phải `AGENTs.md`.
- Không cần copy toàn bộ `.agent/skills` vào `.codex/skills`.
- `.codex/skills/anigravity-skill-loader` sẽ giúp Codex tìm skill phù hợp trong `.agent/skills`.
- `.codex/skills/anigravity-workflow` sẽ giúp Codex đọc workflow tương ứng trong `.agent/workflows`.

## Kiểm tra nhanh

Sau khi copy, trong project nên có cấu trúc tối thiểu:

```text
your-project/
  AGENTS.md
  .codex/
    skills/
      anigravity-skill-loader/
        SKILL.md
      anigravity-workflow/
        SKILL.md
```

Nếu dùng đầy đủ Anigravity, cần thêm:

```text
your-project/
  .agent/
    skills/
    workflows/
    rules/
    .shared/
  GEMINI.md
```
