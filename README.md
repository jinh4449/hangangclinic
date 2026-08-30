# 김포한강한의원 홈페이지 — 배포용

이 저장소에는 **이미 만들어진 HTML** 이 들어 있습니다. Netlify 가 빌드할 것이 없고
파일을 그대로 올리기만 하면 됩니다.

## Netlify 설정

저장소를 연결한 뒤 아래대로 두면 됩니다. `netlify.toml` 에 적혀 있어 그대로 두셔도 됩니다.

| 항목 | 값 |
|---|---|
| Build command | (비움) |
| Publish directory | `.` |

## 무엇이 들어 있나

```
index.html              첫 화면
about.html              병원 소개
care.html               진료과목
care/pain.html          통증치료
care/car-accident.html  교통사고 후유증
care/diet.html          다이어트
care/indigestion.html   소화불량
care/fatigue.html       만성피로
column/*.html           원장 칼럼 10편
part/*.html             부위별 6곳
compare/*.html          비교 3편
doctors.html            의료진 소개
directions.html         오시는 길
reservation.html        예약 · 상담
treatment.html          치료 방법
404.html                없는 주소

_next/                  스타일과 화면 동작에 쓰는 파일
*.txt                   페이지를 미리 받아 두는 자료 — 지우면 링크가 깨집니다
sitemap.xml             검색엔진용 주소 목록
robots.xml / llms.txt   검색엔진·AI 안내
feed.xml                칼럼 RSS
```

## 내용을 고치려면

이 저장소의 HTML 을 직접 고치지 마십시오. 다음에 다시 만들 때 덮어써집니다.

원본은 [`jinh4449/hangang`](https://github.com/jinh4449/hangang) 에 있습니다.
글과 진료시간 같은 내용은 그쪽 `src/content/` 안에 모여 있고, 거기서 고친 뒤
다시 만들어 이 저장소에 올리는 순서입니다.

```bash
# 원본 저장소에서
npm run build          # out/ 에 새 파일이 만들어진다
cp -r out/. ../hangangclinic/
cd ../hangangclinic && git add -A && git commit -m "내용 갱신" && git push
```

## 아직 남은 것

- `sitemap.xml` 과 페이지 안의 구조화 데이터가 아직 `https://example.com` 을 가리킵니다.
  도메인이 정해지면 원본 저장소의 `src/content/clinic.ts` 두 번째 줄을 고치고
  다시 만들어야 검색엔진에 제대로 잡힙니다.
