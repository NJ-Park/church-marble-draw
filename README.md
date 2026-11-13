# 교회 행사 구슬 추첨

GitHub Pages 직접 업로드용으로 빌드한 웹앱입니다. 이 저장소의 Settings → Pages에서 Deploy from a branch / main / (root)를 선택해 게시합니다.

- 첫 화면: `index.html` → `cloud.html` (진행자 로그인)
- 참가 접수: 진행자가 행사 생성 후 표시되는 QR 사용
- 방송: 진행자 화면에서 발급하는 1회용 연결 링크 사용
- 접수·명단·결과: 연결된 Supabase 프로젝트에 저장
- `event.html`: 클라우드와 별개인 로컬 시제품
- `source.zip`: 수정된 전체 소스와 DB 마이그레이션, 개발 설명서

QR 주소는 현재 사이트의 폴더를 사용하므로 GitHub Pages 저장소 주소에서도 동작합니다. 기존 로컬 QR 대신 배포된 진행자 화면의 QR을 사용하세요. URL이나 행사 코드가 바뀌면 QR도 다시 확인하세요.

## 개발 및 업데이트

`source.zip`을 풀고 `CLOUD-README.md`를 참고합니다. `.env.local`은 포함하지 않습니다. 공개 프로젝트 URL·Publishable key를 다시 설정한 뒤 `pnpm build:cloud`로 빌드하세요. 수정 후에는 HTML만이 아니라 새 빌드 파일 전체를 함께 교체해야 합니다. 배포 파일에는 브라우저 연결에 필요한 공개키가 포함되어 있으며 DB 비밀번호·service_role 키는 사용하지 않습니다.

프로젝트 생성·익명 로그인·DB API 응답은 확인했습니다. 실제 진행자 로그인, 휴대폰 등록, Realtime 및 행사장 300명 동시 접수 검증은 배포 후 진행합니다. 공개 행사 전에 CAPTCHA 연결과 익명 로그인 허용량을 확인해야 합니다.

## 원본과 라이선스

Based on [Marble Roulette by lazygyu](https://github.com/lazygyu/roulette), upstream `e9a9d22b040d3acf8f7b581285d1dd39bbe9c2b1`.

MIT License · Copyright (c) 2022 LazyGyu. `LICENSE`, `license.html`, `THIRD_PARTY_NOTICES.txt`를 함께 보존합니다. 행사 앱은 별도 이름을 사용하며 원본 상표는 원저작자에게 귀속됩니다.
