# TRPG Tools

테이블 위를 조금 편하게 만드는 단일 HTML 도구 모음. 서버 없이 GitHub Pages에서 돌아가며, 데이터는 브라우저 localStorage에만 저장됩니다.

- 홈: https://zxcv9561.github.io/trpg-tools/
- **판정 확률 계산기** (파뷸라 울티마): https://zxcv9561.github.io/trpg-tools/calc/
- **핸드아웃 스튜디오** (범용): https://zxcv9561.github.io/trpg-tools/handout/
- **CHAT FX** (Foundry VTT 채팅 효과 매크로 생성기): https://zxcv9561.github.io/trpg-tools/chat-fx/
  - chat-fx 모듈 매니페스트: `https://zxcv9561.github.io/trpg-tools/chat-fx/module/module.json`
    (Foundry 설정 → 모듈 설치 → 매니페스트 URL에 붙여넣기)

## 구조
```
index.html                    # 랜딩
calc/index.html               # 판정 확률 계산기
handout/index.html            # 핸드아웃 스튜디오
chat-fx/index.html            # CHAT FX 생성기
chat-fx/module/module.json    # Foundry 모듈 매니페스트
chat-fx/module/chat-fx.css    # 모듈 스타일시트
chat-fx/module/chat-fx.zip    # 모듈 압축본 (download 대상)
```

## 배포
1. 이 내용을 저장소 루트에 커밋·푸시
2. Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)`

## 모듈 업데이트 절차
`chat-fx.css` 수정 시: `module.json`의 `version`을 올리고, `module/` 안에서
`mkdir chat-fx && cp module.json chat-fx.css chat-fx/ && zip -r chat-fx.zip chat-fx && rm -rf chat-fx`
로 zip을 다시 만들어 함께 푸시하면 Foundry에서 업데이트로 잡힙니다.
