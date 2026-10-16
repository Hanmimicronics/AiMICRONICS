# AI MICRONICS 디자인 시스템 & 스타일 가이드 (Design System & UI Guide)

> **문서 목적**: 앞으로 새로운 페이지, 섹션, 컴포넌트, 또는 서브 프로젝트를 제작할 때 현재 사이트([`micronicsseversite.vercel.app`](https://micronicsseversite.vercel.app/))와 **100% 동일한 시각적 룩앤필(Look & Feel), 타이포그래피, 컬러, 컴포넌트 규칙 및 반응형 레이아웃**을 완벽하게 유지하기 위한 표준 디자인 지침서입니다.
> 
> *AI 에이전트 프롬프트에 이 문서를 첨부하거나 참조시키면 동일한 디자인 퀄리티의 코드를 생성할 수 있습니다.*

---

## 1. 디자인 철학 & 비주얼 톤앤매너

- **Industrial High-Tech & Precision**: 엔터프라이즈 AI 인프라, 고성능 하드웨어(GPU 서버, 랙 마운트, 데이터센터)의 신뢰성과 정밀함을 표현합니다.
- **Deep Contrast Minimalist**: 
  - 딥 블랙(`#050506`, `#08090b`, `#0b0d11`)과 쿨 그레이/페이퍼(`#f7f8fa`, `#eff0f2`, `#ffffff`)의 극명한 대비.
  - 마이크로닉스 시그니처 레드(`#ec1c24`)를 절제된 하이라이트 포인트로 활용.
- **Micro Precision Grid**: 1px 얇은 라인(`--line`, `--line-dark`)으로 면을 분할하고, 카드와 테이블에 정교한 격자 구조를 부여합니다.
- **Tight Typography**: 자간을 조이고(`letter-spacing: -0.04em ~ -0.065em`), `word-break: keep-all` 및 `text-wrap: balance`를 적용하여 단정하고 절제된 한국어/영문 조판을 유지합니다.

---

## 2. 컬러 팔레트 (Color System)

### CSS Variables (`:root`)
```css
:root {
  /* Text & Dark Elements */
  --ink: #11141a;              /* 기본 본문/헤딩 텍스트 (Deep Charcoal/Black) */
  --muted: #626a76;            /* 보조 설명, 서브 텍스트 (Cool Gray) */
  
  /* Backgrounds & Surfaces */
  --surface: #ffffff;          /* 메인 카드 및 콘텐츠 표면 */
  --paper: #f7f8fa;            /* 라이트 섹션 기본 배경 (Subtle Industrial Gray) */
  --surface-accent: #eff0f2;   /* 호버 상태 및 카드 하이라이트 면 */
  
  /* Lines & Dividers */
  --line: #dce0e6;             /* 라이트 모드 기본 경계선 (1px Solid) */
  --line-dark: rgba(255, 255, 255, 0.16); /* 다크 모드 경계선 */

  /* Brand Signature Accent */
  --accent: #ec1c24;           /* 마이크로닉스 시그니처 레드 */
}
```

### 상세 색상표 & 용도

| 색상명 | Hex Code | 용도 / 적용 영역 |
| :--- | :--- | :--- |
| **Micronics Red** | `#ec1c24` | 메인 CTA 버튼, 액센트 라벨, 액티브 인디케이터, 핵심 수치 |
| **Accent Glow / Eyebrow**| `#ff6369` / `#ff4850` | 다크 배경 위의 아이브로우 텍스트, 앰비언트 글로우 |
| **Deep Red / Hover** | `#c7141c` / `#b5151d` | 버튼 호버 상태, 화살표 링크 아이콘, 경고/강조 |
| **Deep Hero Black** | `#050506` / `#08090b` | 최상단 히어로 섹션, 비주얼 배너 배경 |
| **Header / Dark Shell** | `#0b0d11` | 헤더, 푸터, 다크 섹션(협력 모델, 클로징 CTA) 배경 |
| **Card / Surface Dark** | `#11151b` / `#171a20` | Bento Feature 카드 배경, 비교 테이블 헤더, 태그 칩 |
| **Dark Subtext** | `#aab1bd` / `#c5c7cb` | 다크 섹션 본문 텍스트, 네비게이션 미선택 링크 |
| **Hardware Stage** | `#edf0f3` / `#eef0f3` | 서버 랙 및 제품 누끼 이미지를 받쳐주는 쿨 그레이 스테이지 |

---

## 3. 타이포그래피 (Typography)

### 폰트 패밀리
```css
font-family: Pretendard Variable, Pretendard, Noto Sans KR, -apple-system, BlinkMacSystemFont, Segoe UI, Arial, sans-serif;
```
*(숫자 및 영문 강조 섹션: `Helvetica Neue, Helvetica, Arial, sans-serif` 병행)*

### 타이포그래피 계층 & 스타일 가이드

1. **Eyebrow (섹션 카테고리 / 뱃지 라벨)**:
   - 스타일: `font-size: 0.7rem ~ 0.75rem`, `font-weight: 740~760`, `letter-spacing: 0.12em ~ 0.16em`, `text-transform: uppercase`, `color: var(--accent)`
   - 여백: `margin-bottom: 18px ~ 24px`
   - 예시: `ENTERPRISE GPU INFRASTRUCTURE`, `COOPERATION MODEL`

2. **메인 섹션 타이틀 (H1 / H2)**:
   - 스타일: `font-size: clamp(2.0rem, 3.5vw, 3.5rem)`, `font-weight: 660 ~ 680`, `letter-spacing: -0.05em ~ -0.065em`, `line-height: 1.12`
   - 규칙: 반드시 `text-wrap: balance` 및 `word-break: keep-all` 적용

3. **서브 헤딩 / 카드 타이틀 (H3 / H4)**:
   - 스타일: `font-size: clamp(1.2rem, 1.8vw, 1.6rem)`, `font-weight: 620 ~ 650`, `letter-spacing: -0.04em`, `line-height: 1.25`

4. **리드 문장 (Lede / Subtitle)**:
   - 스타일: `font-size: clamp(0.95rem, 1.2vw, 1.05rem)`, `color: var(--muted)` (다크 섹션: `#c5c7cb`), `line-height: 1.75 ~ 1.85`, `max-width: 55ch ~ 62ch`, `text-wrap: pretty`

5. **초대형 숫자 (Hero / Metric Numbers)**:
   - 스타일: `font-size: clamp(2.5rem, 4vw, 3.8rem)`, `font-weight: 700`, `letter-spacing: -0.06em`, `color: var(--accent)`

---

## 4. 레이아웃 & 반응형 규격 (Layout & Breakpoints)

### 기본 컨테이너 (`.shell`)
모든 메인 섹션의 콘텐츠는 최대 너비 `1280px` 컨테이너 안에 배치됩니다.
```css
.shell {
  width: min(calc(100% - 96px), 1280px);
  margin-inline: auto;
}

@media (max-width: 960px) {
  .shell { width: min(calc(100% - 56px), 1280px); }
}

@media (max-width: 760px) {
  .shell { width: min(calc(100% - 40px), 1280px); }
}

@media (max-width: 540px) {
  .shell { width: min(calc(100% - 32px), 1280px); }
}
```

### 섹션 상하 여백 (Vertical Rhythm)
- **표준 섹션 패딩**: `padding-block: clamp(75px, 9vw, 130px);`
- **컴팩트/스트립 섹션**: `padding-block: clamp(50px, 6vw, 85px);`

### 반응형 브레이크포인트 요약
- **Desktop**: `> 960px` (기본 1280px 그리드)
- **Tablet**: `761px ~ 960px` (2컬럼 그리드, 폰트 스케일 다운)
- **Mobile Standard**: `541px ~ 760px` (단일 컬럼 스택, 모바일 햄버거 메뉴)
- **Mobile Small**: `<= 540px` (가로 패딩 16px, 버튼 100% 너비 확장)

---

## 5. UI 컴포넌트 킷 (Component Patterns)

### 1) 버튼 (Buttons)

#### A. Primary Action Button (시그니처 레드 버튼)
```html
<a href="#contact" class="button">
  <span>엔터프라이즈 솔루션 상담</span>
</a>
```
```css
.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 44px;
  padding: 0 20px;
  border: 1px solid var(--accent);
  border-radius: 7px;
  color: #fff;
  background: var(--accent);
  font-size: 0.82rem;
  font-weight: 680;
  line-height: 1;
  white-space: nowrap;
  transition: opacity 0.18s ease, transform 0.18s ease;
  cursor: pointer;
}
.button:hover {
  opacity: 0.88;
  transform: translateY(-1px);
}
```

#### B. Quiet / Outline Button (다크 섹션 보조 버튼)
```html
<a href="#servers" class="button button-quiet">서버 라인업 둘러보기</a>
```
```css
.button-quiet {
  border-color: rgba(255, 255, 255, 0.28);
  color: #fff;
  background: transparent;
}
.button-quiet:hover {
  border-color: #fff;
  background: rgba(255, 255, 255, 0.08);
}
```

#### C. Business Arrow Link (텍스트 링크 + 화살표 애니메이션)
```html
<a href="#detail" class="business-link">
  자세한 사양 확인하기 <span aria-hidden="true">→</span>
</a>
```
```css
.business-link {
  display: inline-flex;
  align-items: center;
  gap: 12px;
  min-height: 44px;
  font-size: 0.9rem;
  font-weight: 650;
  color: inherit;
}
.business-link span {
  color: var(--accent);
  transition: transform 0.2s ease;
}
.business-link:hover span {
  transform: translateX(4px);
}
.business-link:hover {
  text-decoration: underline;
  text-underline-offset: 5px;
}
```

---

### 2) 섹션 헤딩 (Section Heading Pattern)

대부분의 주요 섹션 상단은 **좌측 타이틀 + 우측 설명/버튼**의 2컬럼 레이아웃을 사용합니다.
```html
<div class="business-section-heading">
  <div>
    <p class="eyebrow">HIGH DENSITY HARDWARE</p>
    <h2>차세대 6U / 7U 전용 랙 플랫폼</h2>
  </div>
  <p>
    마이크로닉스의 독자적인 공기역학 설계와 고밀도 전원 설계를 결합하여,
    엔비디아 플래그십 GPU의 최대 성능을 스로틀링 없이 유지합니다.
  </p>
</div>
```
```css
.business-section-heading {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: clamp(30px, 6vw, 90px);
  align-items: start;
  margin-bottom: 50px;
}
@media (max-width: 680px) {
  .business-section-heading {
    grid-template-columns: 1fr;
    gap: 20px;
    margin-bottom: 30px;
  }
}
```

---

### 3) 하드웨어 스테이지 카드 (Product Hardware Card)

서버 랙이나 하드웨어 이미지는 쿨 그레이 배경 위에 곱하기 모드로 배치됩니다.
```html
<article class="server-catalog-card">
  <div class="server-catalog-card-media">
    <img src="/images/micronics-6u-gpu-server.png" alt="Micronics 6U GPU Server" />
  </div>
  <div class="server-catalog-card-copy">
    <div class="server-catalog-card-label">
      <strong>6U</strong>
      <span>DATA CENTER CLASS</span>
    </div>
    <h3>듀얼 Intel/AMD 기반 고성능 6U 서버</h3>
    <p>RTX PRO 6000 Ada 및 H100/H200 GPU 최대 8장 완벽 지원</p>
    
    <dl>
      <div>
        <dt>SUPPORTED GPU</dt>
        <dd>NVIDIA H100 / H200 / RTX PRO 6000 Ada</dd>
      </div>
      <div>
        <dt>COOLING DESIGN</dt>
        <dd>고풍량 핫스왑 팬 모듈 탑재 및 차압 제어 설계</dd>
      </div>
    </dl>
    
    <a href="#inquiry" class="button">상세 견적 요청</a>
  </div>
</article>
```
```css
.server-catalog-card {
  display: grid;
  grid-template-columns: minmax(220px, 0.85fr) minmax(260px, 1.15fr);
  border: 1px solid var(--line);
  background: #f3f5f7;
  border-radius: 8px;
  overflow: hidden;
  transition: transform 0.2s ease, border-color 0.2s ease, box-shadow 0.2s ease;
}
.server-catalog-card:hover {
  transform: translateY(-3px);
  border-color: #b8c0ca;
  background: #f8f9fb;
  box-shadow: 0 12px 30px rgba(17, 20, 26, 0.08);
}
.server-catalog-card-media {
  background: #edf0f3;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 24px;
}
.server-catalog-card-media img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  mix-blend-mode: multiply;
}
.server-catalog-card-copy {
  padding: 28px;
  display: flex;
  flex-direction: column;
}
```

---

### 4) 인더스트리얼 스펙 리스트 (Definition List / Fact Rows)

사양을 표시할 때 사용하는 1px 라인 분할 키-값 리스트입니다.
```html
<dl class="server-facts">
  <div>
    <dt>폼 팩터</dt>
    <dd>표준 19인치 랙 6U / 7U 섀시</dd>
  </div>
  <div>
    <dt>프로세서</dt>
    <dd>Dual 4th/5th Gen Intel® Xeon® Scalable 또는 Dual AMD EPYC™ 9004/9005</dd>
  </div>
  <div>
    <dt>메모리</dt>
    <dd>최대 32개 DDR5 ECC RDIMM 슬롯 (최대 4TB)</dd>
  </div>
  <div>
    <dt>전원 공급 장치</dt>
    <dd>2000W ~ 3200W 80 PLUS Titanium 리던던트 (3+1 / 4+2 구성)</dd>
  </div>
</dl>
```
```css
.server-facts {
  margin: 0;
  border-top: 1px solid var(--line);
}
.server-facts div {
  padding: 16px 0;
  display: grid;
  grid-template-columns: minmax(110px, 0.3fr) 1fr;
  gap: 16px;
  border-bottom: 1px solid var(--line);
}
.server-facts dt {
  color: var(--muted);
  font-size: 0.82rem;
  font-weight: 600;
}
.server-facts dd {
  margin: 0;
  color: var(--ink);
  font-size: 0.9rem;
  font-weight: 550;
}
@media (max-width: 680px) {
  .server-facts div {
    grid-template-columns: 1fr;
    gap: 4px;
  }
}
```

---

### 5) 벤토 피처 카드 (Bento Grid Feature Card - Dark)

```html
<div class="feature-card">
  <div class="feature-card-fallback"></div>
  <div class="feature-card-meta">
    <span>SYSTEM PLATFORM</span>
    <strong>01</strong>
  </div>
  <div class="feature-card-bottom">
    <h3>RTX 5090 8-GPU 네이티브 수용</h3>
    <div class="feature-card-rule"></div>
    <p>블로워 개조 없이 3슬롯 두께의 지포스 그래픽카드를 직접 장착하여 압도적인 연산 비용 절감을 달성합니다.</p>
  </div>
</div>
```
```css
.feature-card {
  position: relative;
  min-height: 290px;
  padding: 28px;
  display: flex;
  flex-direction: column;
  border-radius: 1.25rem;
  overflow: hidden;
  color: #fff;
  background: #11151b;
  box-shadow: 0 14px 30px rgba(17, 20, 26, 0.15);
}
.feature-card-fallback {
  position: absolute;
  inset: 0;
  background: radial-gradient(100% 95% at 50% 108%, rgba(236, 28, 36, 0.33), transparent 58%),
              linear-gradient(145deg, #161d26, #0b0d11 88%);
}
.feature-card-meta, .feature-card-bottom {
  position: relative;
  z-index: 2;
}
.feature-card-meta {
  display: flex;
  justify-content: space-between;
  font-size: 0.78rem;
  letter-spacing: 0.08em;
  color: rgba(255, 255, 255, 0.7);
}
.feature-card-bottom {
  margin-top: auto;
}
.feature-card-bottom h3 {
  margin: 0;
  font-size: 1.35rem;
  font-weight: 600;
  letter-spacing: -0.04em;
}
.feature-card-rule {
  width: 100%;
  height: 1px;
  margin-top: 14px;
  background: rgba(255, 255, 255, 0.18);
}
.feature-card-bottom p {
  margin: 14px 0 0;
  color: rgba(255, 255, 255, 0.85);
  font-size: 0.9rem;
  line-height: 1.68;
}
```

---

### 6) 프로세스 스텝 (Step Card Pattern)

```html
<ol class="process-steps">
  <li>
    <span>STEP 01</span>
    <h3>워크로드 분석</h3>
    <p>요구되는 AI 모델 크기, 배치 사이즈, 추론 레이턴시를 기반으로 최적 하드웨어 구성을 도출합니다.</p>
  </li>
  <li>
    <span>STEP 02</span>
    <h3>장비 빌드 및 테스트</h3>
    <p>김포 본사 팩토리에서 번인 테스트 및 PCIe 대역폭 무결성 검증을 완료합니다.</p>
  </li>
  <li>
    <span>STEP 03</span>
    <h3>데이터센터 입고</h3>
    <p>고객 지정 상면 또는 마이크로닉스 제휴 IDC에 즉시 랙 마운트 및 전력 체결을 진행합니다.</p>
  </li>
  <li>
    <span>STEP 04</span>
    <h3>인프라 운용 지원</h3>
    <p>하드웨어 유지보수, 예비 부품 상시 보유, 긴급 현장 출동 서비스를 지원합니다.</p>
  </li>
</ol>
```
```css
.process-steps {
  list-style: none;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 32px;
  padding: 0;
  margin: 48px 0 0;
}
.process-steps li {
  border-top: 1px solid var(--line);
  padding-top: 24px;
}
.process-steps li > span {
  color: var(--accent);
  font-size: 0.75rem;
  font-weight: 720;
  letter-spacing: 0.08em;
}
.process-steps h3 {
  margin: 18px 0 10px;
  font-size: 1.25rem;
  font-weight: 650;
  letter-spacing: -0.035em;
  color: var(--ink);
}
.process-steps p {
  margin: 0;
  color: var(--muted);
  font-size: 0.88rem;
  line-height: 1.75;
}
@media (max-width: 960px) {
  .process-steps { grid-template-columns: repeat(2, 1fr); }
}
@media (max-width: 680px) {
  .process-steps { grid-template-columns: 1fr; }
}
```

---

### 7) 아코디언 / FAQ (Accordion Details)

```html
<div class="faq-list">
  <details>
    <summary>
      <span>단기 프로젝트 단위로도 임대가 가능한가요?</span>
      <span class="faq-toggle" aria-hidden="true">+</span>
    </summary>
    <p>네, 최소 1개월 단위의 단기 프로젝트부터 다년간의 장기 전용 클러스터 구성까지 유연한 계약 조건을 제공합니다.</p>
  </details>
  <details>
    <summary>
      <span>소비자용 GPU(RTX 4090/5090) 발열 제어는 안전한가요?</span>
      <span class="faq-toggle" aria-hidden="true">+</span>
    </summary>
    <p>마이크로닉스 7U 섀시는 각 GPU마다 독립 흡배기 터널과 6,000 RPM 고정압 핫스왑 팬 모듈을 갖추고 있어 24/7 풀로드 상태에서도 적정 온도를 엄격히 유지합니다.</p>
  </details>
</div>
```
```css
.faq-list details {
  border-bottom: 1px solid var(--line);
}
.faq-list details:first-child {
  border-top: 1px solid var(--line);
}
.faq-list summary {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
  padding: 24px 0;
  cursor: pointer;
  font-weight: 600;
  font-size: 1.05rem;
  color: var(--ink);
  list-style: none;
}
.faq-list summary::-webkit-details-marker {
  display: none;
}
.faq-toggle {
  font-size: 1.4rem;
  color: var(--accent);
  transition: transform 0.2s ease;
}
.faq-list details[open] .faq-toggle {
  transform: rotate(45deg);
}
.faq-list p {
  color: var(--muted);
  font-size: 0.92rem;
  line-height: 1.8;
  margin: 0 0 24px 0;
  max-width: 70ch;
}
```

---

## 6. 카피라이팅 가이드라인 (Copywriting & Tone)

1. **엔터프라이즈 B2B 문체 유지**:
   - 가볍거나 캐주얼한 표현을 지양하고, **전문적이고 확신에 찬 어조**(~합니다, ~를 지원합니다)를 사용합니다.
2. **사양과 가치를 명확히 제시**:
   - 추상적인 수식어("매우 뛰어난 성능")보다는 구체적인 플랫폼 스펙("PCIe 5.0 x16 풀 대역폭 지원", "핫스왑 티타늄 리던던트 파워 4+2 구성")을 앞세웁니다.
3. **용어 통일**:
   - 한미마이크로닉스, Micronics, GPU 인프라, 베어메탈, 코로케이션, 6U 랙 서버, 7U 랙 서버, NVIDIA H100/H200, RTX 5090
4. **한글 조판 원칙**:
   - 제목 및 본문 태그에 `word-break: keep-all;`을 필수로 적용하여 단어가 줄바꿈 도중 중간에 잘리지 않도록 합니다.

---

## 7. 신규 페이지 제작 시 기본 HTML 보일러플레이트

```html
<!doctype html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>[페이지 제목] | Micronics 기업용 GPU 인프라</title>
    
    <!-- Pretendard Variable CDN -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/variable/pretendardvariable-dynamic-subset.css" />
    
    <!-- 디자인 시스템 스타일 링크 (또는 컴파일된 CSS) -->
    <link rel="stylesheet" href="/assets/index-BeNHMa9z.css" />
  </head>
  <body class="site-frame" data-language="ko">
    
    <!-- 사이트 헤더 -->
    <header class="site-header">
      <a href="/" class="brand-logo-link" aria-label="Micronics 홈">
        <img src="/images/micronics-logo.png" alt="Micronics" class="brand-logo brand-logo-header" />
      </a>
      <nav class="desktop-nav" aria-label="메인 네비게이션">
        <a href="#resources">GPU 자원</a>
        <a href="#servers">서버 라인업</a>
        <a href="#solutions">솔루션</a>
        <a href="#pricing">견적 안내</a>
        <a href="#about">마이크로닉스 소개</a>
      </nav>
      <div class="header-tools">
        <a href="#contact" class="header-contact">도입 문의</a>
      </div>
    </header>

    <main>
      <!-- 섹션 템플릿 -->
      <section class="server-platform">
        <div class="shell">
          <div class="business-section-heading">
            <div>
              <p class="eyebrow">ENTERPRISE SOLUTION</p>
              <h2>새로운 페이지 섹션 타이틀</h2>
            </div>
            <p>
              마이크로닉스 기업용 GPU 인프라 표준 디자인 가이드에 맞춰 작성된 본문 영역입니다.
            </p>
          </div>
          
          <!-- 카드 그리드 또는 콘텐츠 영역 -->
          
        </div>
      </section>
    </main>

    <!-- 사이트 푸터 -->
    <footer class="footer">
      <div class="shell footer-shell">
        <div class="footer-brand">
          <img src="/images/micronics-logo.png" alt="Micronics" class="brand-logo-footer" />
          <p>한미마이크로닉스 | 기업 AI 인프라 구축 솔루션</p>
        </div>
        <div class="footer-company">
          <p class="footer-label">HEADQUARTERS</p>
          <p>경기도 김포시 양촌읍 삼도로48번길 72<br />대표전화: 1522-6399 | service@micronics.co.kr</p>
        </div>
        <div class="footer-bottom">
          <p>© Hanmi Micronics Co., Ltd. All rights reserved.</p>
        </div>
      </div>
    </footer>

  </body>
</html>
```

---

## 8. 향후 작업 시 AI 프롬프트 지시 템플릿 (복사해서 사용)

AI에게 새로운 페이지나 컴포넌트 추가를 요청할 때는 다음 문구를 붙여넣어 실행하세요:

```text
[디자인 일관성 지침 준수 요청]
반드시 작업 폴더의 `DESIGN_SYSTEM.md`에 정의된 규격을 철저히 준수하여 디자인을 구현해 주세요:
1. 컬러: Deep Black(#050506, #0b0d11), Paper(#f7f8fa), Micronics Red(#ec1c24, --accent), Cool Gray(#edf0f3)
2. 폰트: Pretendard Variable, letter-spacing: -0.04em ~ -0.065em, word-break: keep-all, text-wrap: balance
3. 컨테이너: .shell (max-width 1280px)
4. UI 톤: 하이테크 B2B 엔터프라이즈 감성, 1px 보더 분할선, 쿨 그레이 스테이지 누끼 처리
```
