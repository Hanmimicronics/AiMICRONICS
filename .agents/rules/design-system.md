---
trigger: always_on
description: Mandatory rule to enforce DESIGN_SYSTEM.md guidelines for any frontend/web page creation or modification.
---

# Design System Enforcement Rule

Whenever creating, editing, styling, or designing any web page, HTML, CSS, component, or layout in this workspace:

1. **Mandatory Step**: You MUST read and strictly follow [`DESIGN_SYSTEM.md`](../../DESIGN_SYSTEM.md) before writing or editing code.
2. **Colors**: Always adhere to the established palette:
   - Primary Accent: `#ec1c24` (`--accent`)
   - Dark Background: `#050506`, `#0b0d11`, `#11151b`
   - Light Background: `#ffffff`, `#f7f8fa`, `#edf0f3`
   - Borders: `--line: #dce0e6` (1px solid)
3. **Typography**: Pretendard Variable, tight Korean tracking (`letter-spacing: -0.05em`), and `word-break: keep-all;`.
4. **Layout**: Maximum width container `.shell` (1280px).
5. **No Deviations**: Never inject random Bootstrap, Tailwind default colors, or generic styling that breaks the high-tech enterprise identity of Hanmi Micronics.
