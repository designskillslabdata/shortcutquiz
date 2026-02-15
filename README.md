# 단축키 퀴즈 PWA 배포 가이드

## 📁 파일 구성
```
├── index.html     ← 퀴즈 메인 페이지 (PWA + 단축키 차단 적용)
├── manifest.json  ← PWA 앱 설정
├── sw.js          ← Service Worker (오프라인 지원)
├── icon-192.png   ← 앱 아이콘 (직접 추가 필요)
├── icon-512.png   ← 앱 아이콘 (직접 추가 필요)
└── README.md
```

## 🚀 배포 순서

### 1단계: 아이콘 파일 준비
- `icon-192.png` (192×192px)
- `icon-512.png` (512×512px)
- 디자인 스킬 랩 로고 이미지를 해당 크기로 저장해서 이 폴더에 넣으세요.

### 2단계: GitHub에 올리기
이 폴더의 파일들을 `designskillslabdata/designslab` 저장소에 추가하거나,
새로운 저장소 `shortcut-quiz`를 만들어서 업로드하세요.

```bash
# 새 저장소를 만든 경우
git init
git add .
git commit -m "PWA 퀴즈 초기 배포"
git remote add origin https://github.com/designskillslabdata/shortcut-quiz.git
git push -u origin main
```

### 3단계: GitHub Pages 활성화
1. GitHub 저장소 → Settings → Pages
2. Source: `main` 브랜치, `/ (root)` 선택
3. Save 클릭
4. 배포 완료 후 주소: `https://designskillslabdata.github.io/shortcut-quiz/`

### 4단계: 아임웹에서 연결
아임웹 단축키 페이지에 버튼 추가:
```html
<a href="https://designskillslabdata.github.io/shortcut-quiz/" 
   target="_blank">
  🎮 단축키 퀴즈 시작 (전체화면 권장)
</a>
```

## ✅ 해결되는 문제들
- `Ctrl+W` (탭 닫기) → 차단됨
- `Ctrl+T` (새 탭) → 차단됨  
- `Ctrl+F` (브라우저 찾기) → 차단됨
- `Ctrl+P` (인쇄) → 차단됨
- `Ctrl+R` (새로고침) → 차단됨
- 기타 모든 Ctrl/Alt/Meta 조합 → 차단됨

## 📱 PWA 설치 후 동작
- 전체화면으로 실행 (브라우저 UI 없음)
- 탭바가 없으므로 Ctrl+W, Ctrl+T 자체가 무의미해짐
- 데스크탑 앱처럼 동작
