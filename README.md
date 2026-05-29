# ESDM JAR 계획 생성기

## 배포 구조
```
esdm-jar-app/
├── public/
│   └── index.html      ← 프론트엔드
├── api/
│   └── generate.js     ← Anthropic API 프록시 (키 보호)
├── vercel.json         ← Vercel 라우팅 설정
└── README.md
```

## Vercel 배포 방법

### 1단계 — GitHub 업로드
1. github.com 접속 → New repository
2. Repository name: `esdm-jar-app` (Public)
3. 이 폴더 안의 파일 전체를 업로드

### 2단계 — Vercel 연결
1. vercel.com 접속 → Sign up (GitHub 계정으로)
2. "Add New Project" → GitHub 저장소 선택
3. "Import" 클릭

### 3단계 — API 키 설정 (중요)
1. Vercel 프로젝트 → Settings → Environment Variables
2. 아래 항목 추가:
   - Name: `ANTHROPIC_API_KEY`
   - Value: `sk-ant-...` (실제 키 붙여넣기)
   - Environment: Production, Preview, Development 모두 체크
3. Save 클릭

### 4단계 — 배포
1. Vercel → Deployments → "Redeploy" 클릭
2. 완료되면 `https://esdm-jar-app.vercel.app` 링크 생성

## API 키 발급
https://console.anthropic.com → API Keys → Create Key
