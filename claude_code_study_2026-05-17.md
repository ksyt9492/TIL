# Claude Code 학습 노트
> 날짜: 2026-05-17

---

## 1. GitHub에서 `.claude` 폴더가 안 보이는 이유

### 원인
- 리눅스/맥에서 `.`으로 시작하는 폴더는 **숨김 처리**됨
- ZIP 다운로드 시 `.claude` 폴더가 **누락**되는 경우 있음

### 해결 방법

#### ✅ 권장: git clone 사용
```bash
git clone https://github.com/claude-code-expert/example.git
cd example
ls -la   # 숨김 폴더 포함 전체 표시
```

#### ZIP 다운로드 후 숨김 파일 보기
```bash
# 터미널에서
ls -la       # .claude 보임
ls -la .claude/

# Ubuntu 파일 관리자(Nautilus)에서
Ctrl + H     # 숨김 파일 토글
```

---

## 2. claude-code-expert/example 저장소 `.claude` 구조

```
.claude/
├── commands/
│   ├── optimize.md
│   └── security-checklist.md
├── hooks/
│   ├── __pycache__/
│   │   ├── check-deps-py.cpython-311.pyc
│   │   └── pre-tool-guard.cpython-311.pyc
│   ├── block-dangerous.py       # 위험 명령어 차단
│   ├── check-deps-py.py         # Python 의존성 체크
│   ├── format-py.sh             # Python 포맷
│   ├── format-ts.sh             # TypeScript 포맷
│   ├── lint-py.sh               # Python 린트
│   ├── lint-ts.sh               # TypeScript 린트
│   ├── notify-slack.sh          # Slack 알림
│   ├── notify-telegram.sh       # Telegram 알림
│   ├── settings.python.json     # Python 훅 설정
│   ├── settings.typescript.json # TypeScript 훅 설정
│   ├── test-py.sh               # Python 테스트
│   └── test-ts.sh               # TypeScript 테스트
├── rules/
│   ├── README.md
│   ├── api-routes.md
│   ├── database.md
│   ├── frontend.md
│   └── testing.md
└── settings.json
```

---

## 3. rules 폴더 파일 확인 방법

```bash
# 개별 파일 보기
nvim .claude/rules/README.md

# 전체 한 번에 보기
for f in .claude/rules/*.md; do echo "=== $f ==="; cat "$f"; echo; done
```

---

## 4. 다음 학습 예정

- `.claude/hooks/` 폴더 상세 학습
  - `block-dangerous.py` : 위험한 명령어 차단 훅
  - `check-deps-py.py` : Python 의존성 체크 훅
  - `settings.json` : 훅 등록 구조 확인

---

## 참고 저장소

- [claude-code-expert/example](https://github.com/claude-code-expert/example)
- 설명: 클로드 코드 설정 및 마크다운 예제 모음


cd ~/문서/TIL

# 파일 삭제
git rm 파일명.md

# 커밋
git commit -m "파일 삭제"

# push
git push origin main



# 1. TIL 폴더로 이동
cd ~/문서/TIL

# 2. 파일 열어서 내용 추가
nvim 파일명.md

# 3. 저장 후 나오기 (nvim에서)
# i 로 입력모드 → 내용 작성 → ESC → :wq

# 4. 스테이징
git add 파일명.md

# 5. 커밋
git commit -m "내용 추가"

# 6. push
git push origin main




