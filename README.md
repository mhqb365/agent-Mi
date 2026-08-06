# Agent Pack for Mi & Ponytail

Repo này chứa 2 phong cách làm việc cho Codex và Antigravity

- `Mi`: mặc định, dùng cấu hình Anigravity/Gemini và áp dụng nguyên tắc Ponytail-style: tối giản, ít token, hiệu quả cao
- `Ponytail`: profile phụ, dùng khi người dùng explicitly yêu cầu mode lazy senior dev

## Repo này có gì

```text
AGENTS.md
AGENTS_CODEX.md
GEMINI.md
.agent/
.codex/
```

## Cách dùng

- Copy toàn bộ thư mục này vào thư mục gốc của dự án
- Không cần cấu hình thêm
- Agent sẽ tự đọc `AGENTS.md`, `AGENTS_CODEX.md` và `GEMINI.md` để hoạt động
- Với Mi / Antigravity, agent đọc `AGENTS_CODEX.md` và `GEMINI.md`
- Với Ponytail, agent dùng `AGENTS.md` như rule chính khi được kích hoạt rõ ràng

## Lưu ý

- `AGENTS.md` là router chính và đặt Mi là profile mặc định
- `GEMINI.md` là cấu hình tham chiếu cho Mi/Anigravity
- Nếu project đích cần đầy đủ skill/workflow Anigravity, cần có thêm `.agent/` và `.codex/`
