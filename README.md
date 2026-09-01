# 김포한강한의원 홈페이지 — 배포용

이 저장소에는 **이미 만들어진 HTML** 이 들어 있습니다. 빌드할 것이 없고
파일을 그대로 올리기만 하면 됩니다.

## Cloudflare Pages 설정

Workers & Pages → Create → Pages → Connect to Git → 이 저장소 선택.
그다음 아래대로 두면 됩니다.

| 항목 | 값 |
|---|---|
| Production branch | `main` |
| Framework preset | **None** |
| Build command | **(비움)** |
| Build output directory | `/` |

빌드 명령을 비워 두는 것이 중요합니다. 여기 있는 것은 결과물이라
다시 만들 필요가 없고, 빌드를 걸면 실패합니다.

캐시 규칙은 `_headers` 에 있습니다. 이 파일은 원본 저장소의 `public/_headers`
에서 만들어지므로 **여기서 고치면 다음 배포에 지워집니다.**

`netlify.toml` 은 Netlify 로 되돌아갈 때를 위해 남겨 두었습니다.
Cloudflare 는 이 파일을 읽지 않습니다.

## 무엇이 들어 있나

```
index.html              첫 화면
about.html              병원 소개
care.html               진료과목
care/*.html             통증 · 교통사고 · 다이어트 · 소화불량 · 만성피로
area.html               동네별 오시는 길
area/*.html             김포시 동네 16곳
column/*.html           원장 칼럼
part/*.html             부위별 6곳
compare/*.html          비교 3편
doctors.html            의료진 소개
directions.html         오시는 길
reservation.html        예약 · 상담
treatment.html          치료 방법
404.html                없는 주소

_next/                  스타일과 화면 동작에 쓰는 파일
_headers                캐시 규칙
*.txt                   페이지를 미리 받아 두는 자료 — 지우면 링크가 깨집니다
sitemap.xml             검색엔진용 주소 목록
robots.txt / llms.txt   검색엔진 · AI 안내
feed.xml                칼럼 RSS
version.txt             지금 올라간 판 (커밋 번호와 만든 시각)
```

## 내용을 고치려면

이 저장소의 HTML 을 직접 고치지 마십시오. 다음에 다시 만들 때 덮어써집니다.

원본은 [`jinh4449/hangang`](https://github.com/jinh4449/hangang) 에 있습니다.
글과 진료시간 같은 내용은 그쪽 `src/content/` 안에 모여 있습니다.
거기서 고친 뒤 아래 한 줄이면 여기까지 올라갑니다.

```bash
./tools/deploy.sh "무엇을 고쳤는지"
```

## 제대로 올라갔는지 확인

`/version.txt` 를 열면 지금 올라가 있는 판의 커밋 번호와 만든 시각이 나옵니다.
「고쳤는데 왜 그대로냐」 싶을 때 이 주소부터 보십시오.
