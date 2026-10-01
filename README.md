
# Integration PLC Logic View — PLC Ladder Viewer & Simulator

**🔗 Live: https://ladder-view-demo.vercel.app/**

브라우저에서 바로 쓰는 **PLC 래더 다이어그램 뷰어 & 시뮬레이터**입니다. 설치 없이 각 벤더 툴의 프로젝트 파일이나 내보내기 파일을 업로드하면 래더를 바로 렌더링하고 FB를 시각화하며, Mitsubishi 래더는 통전 시뮬레이션·자동 검수·인터록 분석까지 지원합니다.

A free, browser-based **PLC ladder diagram viewer and simulator**. Upload vendor project or export files — no installation required. Ladder rendering for Mitsubishi, Keyence, Siemens and LS Electric; soft-scan simulation and inspection for Mitsubishi GX Works3.

## 지원 벤더 (Supported Vendors)

| 벤더 | 도구 | 포맷 | 래더 렌더 | 통전 시뮬 |
|---|---|---|:---:|:---:|
| Mitsubishi | GX Works3 | **프로젝트 파일 `.gx3` 직접 임포트** · IL CSV · 디바이스 코멘트 CSV · FB(Function Block) | ✅ | ✅ |
| Keyence | KV STUDIO | 니모닉 `.mnm` | ✅ | — |
| Siemens | TIA Portal | TIA Openness XML — FB/OB 래더(LAD) + DB/UDT/PLC Tags 자산 뷰 | ✅ | — |
| LS Electric | XG5000 | **프로젝트 파일 `.xgwx` 직접 임포트** · 프로그램 `.pra`(XGK) / `.pri`(XGI) (베타) | ✅ | — |

> 통전 시뮬레이션·자동 검수·타임차트·인터록 분석은 현재 **Mitsubishi(GX Works3)** 래더에서 동작합니다. 다른 벤더는 렌더·FB 시각화 중심이며, Siemens SCL 네트워크는 플레이스홀더로 표시됩니다.

## 주요 기능 (Features)

- 🗂️ **프로젝트 파일 직접 임포트** — GX Works3 `.gx3`, XG5000 `.xgwx`를 내보내기 없이 바로 열기 (디바이스 코멘트 자동 연동, POU ▸ 섹션 트리)
- 🧩 **FB 시각화** — GX Works3 FB 인스턴스, TIA Call, XG5000 XGI FB 인스턴스를 핀 블록으로 렌더링
- ⚡ **통전 시뮬레이션 (Mitsubishi)** — 소프트 스캔 엔진으로 접점·코일 통전, 타이머/카운터 실시간 확인
- ✅ **자동 검수 (Mitsubishi)** — 이중코일, 태그 표준화, 임시접점, 실 I/O 검사
- 📊 타임차트 · 대시보드 · 인터록 분석 (시뮬레이션 기반)
- 📱 모바일 반응형 · 🌐 한국어/영어 · 라이트/다크 테마

## 키워드

PLC ladder viewer, ladder diagram, ladder logic simulator, 래더 뷰어, 래더 시뮬레이터,
GX Works3, KV STUDIO, TIA Portal, XG5000, Mitsubishi PLC, Keyence PLC, Siemens PLC, LS Electric PLC,
gx3 viewer, xgwx viewer, TIA Openness XML, IL parser, instruction list, 미쓰비시 래더, 지멘스 래더, PLC 로직 뷰어

## 개발자 (Author)

**김민준 (MinJun Kim)** — PLC 자동화 SW·HW 기업의 프론트엔드 개발자
📫 kimmj21111@gmail.com · [GitHub](https://github.com/MinJunKimsdaads)

## 벤더별 가이드 (Vendor Guides)

- [Mitsubishi 래더 뷰어 — GX Works3 .gx3 / CSV](https://ladder-view-demo.vercel.app/guides/mitsubishi-ladder-viewer.html)
- [Siemens 래더 뷰어 — TIA Portal XML](https://ladder-view-demo.vercel.app/guides/siemens-ladder-viewer.html)
- [Keyence 래더 뷰어 — KV STUDIO .mnm](https://ladder-view-demo.vercel.app/guides/keyence-ladder-viewer.html)
- [LS Electric 래더 뷰어 — XG5000 .xgwx / .pra / .pri](https://ladder-view-demo.vercel.app/guides/ls-electric-ladder-viewer.html)

## 패치노트 (Changelog)

### 2026-09-17
- **GX Works3 `.gx3` 임포트 고도화**
  - 프로그램/FB 표시명 복원 — 암호화된 이름 테이블 없이 FB 호출부 역산으로 실명 표시, 톱 프로그램은 타이틀 폴백
  - EM 목록을 GX Works3 내비게이션과 같은 **POU ▸ 섹션 트리**로 표시 (접기/펼치기)
  - 상승/하강 펄스 접점, 비트 지정·인덱스 수식 디바이스(예: `SD1504.0Z10`), 코일 추가 피연산자(`OUT T71 K5`) 렌더 수정
  - `.gx3` 내 디바이스 코멘트(DC.db) 자동 연동 — 접점/블록 아래 코멘트 표시

### 2026-09-08
- **프로젝트 파일 직접 임포트** — 내보내기 없이 원본 프로젝트 파일을 바로 열기
  - Mitsubishi **GX Works3 `.gx3`**: ZIP+SQLite 컨테이너 해석, 라벨·FB 호출·비교 접점 렌더 (브라우저 sql.js)
  - LS Electric **XG5000 `.xgwx`**: gzip+bzip2 중첩 압축 해석, 프로그램별 래더 로드

### 2026-09-03
- 래더 캔버스 색을 브랜드 테마(teal 계열)로 통일

### 2026-08-21
- 뷰어 모바일 반응형 — 사이드바 드로어, 컴팩트 헤더, I/O 하단 시트

### 2026-08-20
- **LS XGI(.pri) 지원** — 태그 기반 프로그램, TON 인스턴스, SET/RST 코일 확정
- 벤더별 SEO 가이드 페이지 4종 추가, 인앱 피드백 버튼

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
