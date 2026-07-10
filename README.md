# Agent Pack for Ponytail and Mi

Repo này chứa 2 bộ hướng dẫn cho Codex:

- `Ponytail`: bộ skill/rule tối giản, ưu tiên diff nhỏ và tái sử dụng.
- `Mi`: bộ cấu hình Anigravity/Gemini, gồm `AGENTS_CODEX.md`, `GEMINI.md` và các file liên quan đến `.agent/`.

## Repo này có gì

```text
AGENTS.md
AGENTS_CODEX.md
GEMINI.md
skills/
```

## Cách dùng

### Với Ponytail

Khi làm việc theo profile `Ponytail`, Codex sẽ đọc `AGENTS.md` và áp dụng các rule trong file này.

### Với Mi / Anigravity

Khi người dùng gọi `Mi`, nhắc đến Anigravity, `.agent`, `.codex`, hoặc slash commands, Codex sẽ đọc `AGENTS_CODEX.md` trước và dùng `GEMINI.md` như knowledge pack tham chiếu.

## Cấu trúc skill hiện có

```text
skills/
  ponytail/
  ponytail-audit/
  ponytail-debt/
  ponytail-gain/
  ponytail-help/
  ponytail-review/
```

## Lưu ý

- `AGENTS.md` là file rule chính cho Codex trong workspace.
- `GEMINI.md` là cấu hình tham chiếu cho Mi/Anigravity.
- Nếu project đích cần dùng đầy đủ Anigravity skills/workflows, cần có thêm `.agent/` và `.codex/` theo đúng cấu trúc của project đó.
