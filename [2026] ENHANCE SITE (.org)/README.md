# ENHANCE Institute Website
## Deployment Guide for Netlify

### 파일 구조
```
enhance-website/
├── index.html        ← 메인 랜딩
├── about.html        ← ENHANCE 소개 + 철학
├── services.html     ← 서비스 목록
├── research.html     ← 보고서 (날짜 기반 자동 공개)
├── contact.html      ← 문의
├── style.css         ← 공통 스타일시트
└── images/
    ├── enhance-logo.png   ← ENHANCE 로고
    └── orca-emblem.png    ← ORCA 엠블럼
```

### Netlify 배포 방법
1. 이 폴더 전체를 GitHub 리포지토리에 푸시
2. Netlify에서 해당 리포지토리 연결
3. Build command: 없음 (static site)
4. Publish directory: / (루트)

### 4월 7일 당일 해야 할 것 (research.html)
1. `research.html` 파일 열기
2. 다음 줄 찾기:
   ```javascript
   const REPORT_URL = '#'; // TODO: replace with actual PDF URL on April 7
   ```
3. '#' 을 실제 PDF 링크로 교체:
   ```javascript
   const REPORT_URL = 'https://your-pdf-link.com/sii-2026.pdf';
   ```
4. 저장 후 Netlify에 푸시 → 자동 배포

### 4월 15일 당일 해야 할 것 (research.html)
1. `CASE_URL` 을 케이스 분석 PDF 링크로 교체
2. 저장 후 푸시

### 날짜 로직 설명
- research.html은 자동으로 현재 날짜를 감지
- 4월 7일 이전: "Coming April 7" 버튼 표시
- 4월 7일 이후: "Download PDF" 버튼 자동 활성화
- 4월 15일 이후: 케이스 분석도 자동 활성화

### 색상 (CSS 변수)
- Teal:  #009B8D
- Navy:  #3D5068
- Black: #0A0A0A
- White: #FFFFFF
