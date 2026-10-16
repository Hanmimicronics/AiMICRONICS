# AI MICRONICS 프로젝트 워크스페이스 규칙 (Workspace Mandatory Rules)

> **[최우선 필수 지침 (MANDATORY DIRECTIVE)]**
> 이 워크스페이스에서 웹페이지, HTML, CSS, 컴포넌트, 섹션을 신규 제작하거나 기존 페이지를 수정/유지보수할 때는,
> **코드를 작성하거나 수정하기 전에 무조건 [`DESIGN_SYSTEM.md`](./DESIGN_SYSTEM.md)를 먼저 확인하고 규격을 100% 준수해야 합니다.**
> 예외 없이 모든 UI/UX 및 웹 개발 작업에 상시 적용됩니다.

---

## 1. 디자인 일관성 유지 원칙 (Design Consistency)
- **독자적이거나 임의의 스타일 적용 금지**: 부트스트랩, 기본 테일윈드 기본값 등 이질적인 스타일을 임의로 주입하지 마십시오.
- **철저한 브랜드 아이덴티티 준수**: 한미마이크로닉스 엔터프라이즈 GPU 인프라 전용 디자인 시스템을 엄격히 적용합니다.

## 2. 필수 준수 항목 (`DESIGN_SYSTEM.md` 기반)
1. **컬러 시스템**:
   - Primary Accent: `#ec1c24` (`--accent`)
   - Accent Eyebrow / Sub: `#ff6369` / `#c7141c`
   - Dark Base: `#050506` (히어로), `#0b0d11` (헤더/푸터/다크 섹션), `#11151b` (Bento 카드)
   - Light Base: `#ffffff` (표면), `#f7f8fa` (`--paper`), `#edf0f3` (하드웨어 제품 스테이지)
   - 분할선: `--line: #dce0e6` (1px 고정밀 분할선), 다크 분할선 `rgba(255, 255, 255, 0.16)`
2. **타이포그래피**:
   - 폰트: `Pretendard Variable` (본문/헤딩), `Helvetica Neue` (영문/숫자)
   - 한글 자간: 대제목 `letter-spacing: -0.05em ~ -0.065em`
   - 줄바꿈: `word-break: keep-all;` (한글 단어 쪼개짐 방지 필수), `text-wrap: balance;` (헤딩), `text-wrap: pretty;` (본문)
   - Eyebrow 카테고리 라벨: `font-size: 0.7rem`, `font-weight: 750`, `letter-spacing: 0.12em`, 대문자 및 레드 컬러
3. **레이아웃 & 컨테이너**:
   - 최대 너비: `.shell` (`width: min(calc(100% - 96px), 1280px); margin-inline: auto;`)
   - 헤더: 높이 76px (모바일 65px), 다크 테마
4. **UI 컴포넌트 스타일**:
   - 버튼(`.button`, `.button-quiet`, `.business-link`), 카드, 2컬럼 섹션 헤딩, 사양 리스트(DL), Bento 그리드 등은 반드시 `DESIGN_SYSTEM.md`의 표준 컴포넌트 마크업 및 클래스를 재사용합니다.

## 3. 작업 전 필수 체크리스트
- [ ] 작업을 시작하기 전 `DESIGN_SYSTEM.md`를 열어 관련 컴포넌트 및 CSS 규격을 확인했는가?
- [ ] 신규 작성/수정된 코드가 `DESIGN_SYSTEM.md`의 색상 변수, 폰트 자간, 패딩, 반응형 분기점을 그대로 따르고 있는가?
- [ ] 한글 텍스트에 `word-break: keep-all;`이 적용되어 가독성이 유지되는가?
