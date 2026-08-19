# Integration PLC Logic View — PLC Ladder Viewer & Simulator

**🔗 Live: https://ladder-view-demo.vercel.app/**

브라우저에서 바로 쓰는 **PLC 래더 다이어그램 뷰어 & 시뮬레이터**입니다. 설치 없이 각 벤더 툴의 내보내기 파일을 업로드하면 래더 렌더링, 통전 시뮬레이션, FB 시각화, 자동 검수를 제공합니다.

A free, browser-based **PLC ladder diagram viewer and simulator**. Upload vendor export files — no installation required.

## 지원 벤더 (Supported Vendors)

| 벤더 | 도구 | 포맷 |
|---|---|---|
| Mitsubishi | GX Works3 | IL CSV · 디바이스 코멘트 CSV · FB(Function Block) |
| Keyence | KV STUDIO | 니모닉 `.mnm` |
| Siemens | TIA Portal | TIA Openness XML (FB/OB/DB/PLC Tags) |
| LS Electric | XG5000 | 프로그램 `.pra` (베타) |

## 주요 기능 (Features)

- ⚡ **통전 시뮬레이션** — 소프트 스캔 엔진으로 접점·코일 통전, 타이머/카운터 실시간 확인
- 🧩 **FB 시각화** — GX Works3 FB 인스턴스, TIA Call을 핀 블록으로 렌더링
- ✅ **자동 검수** — 이중코일, 태그 표준화, 임시접점, 실 I/O 검사
- 📊 타임차트 · 대시보드 · 인터록 분석
- 🌐 한국어/영어, 라이트/다크 테마

## 키워드

PLC ladder viewer, ladder diagram, ladder logic simulator, 래더 뷰어, 래더 시뮬레이터,
GX Works3, KV STUDIO, TIA Portal, XG5000, Mitsubishi PLC, Keyence PLC, Siemens PLC, LS Electric PLC,
IL parser, instruction list, 미쓰비시 래더, 지멘스 래더, PLC 로직 뷰어

## 개발자 (Author)

**김민준 (MinJun Kim)** — PLC 자동화 SW·HW 기업의 프론트엔드 개발자
📫 kimmj21111@gmail.com · [GitHub](https://github.com/MinJunKimsdaads)

## 패치노트 (Changelog)

### 2026-08-19
- **LS Electric (XG5000) 지원** — `.pra` 바이너리 포맷 분석, 접점/코일/FB/분기 렌더링 (베타)

### 2026-08-18
- 랜딩 개편 (히어로 애니메이션, 원클릭 샘플 체험), 접근성(WCAG AA)·반응형 개선
- IL Emitter — IR→IL 역변환 + 라운드트립 검증

### 2026-08-14
- Siemens TIA Portal 지원 — Openness XML 파싱, FB/OB 래더 + DB/UDT/태그 자산 뷰
- SEO 및 Google Search Console 등록

### 2026-08-13
- Mitsubishi FB(Function Block) 렌더링 + 배선 시뮬레이션
- Keyence KV STUDIO `.mnm` 지원, 벤더 선택 랜딩
