# 1986피트니스 가양점 랜딩페이지

가양역 6·7번 출구 앞 24시간 헬스장 소개 페이지입니다. 별도 빌드 과정 없이 정적 파일만으로 동작하며 GitHub Pages에서 바로 서비스됩니다.

현재 주소: <https://1986-fitness-gayang.github.io>

## 구성

| 파일 | 내용 |
| --- | --- |
| `index.html` | 메인 — 시설 슬라이드, 센터 소개 영상, 소식, 트레이너, PT 후기, 오시는 길, Q&A |
| `trainer-*.html` | 트레이너 5인 개별 페이지 (이력·자격, 수업 영상, Before & After) |
| `assets/` | 사진·영상 원본 (회원 얼굴은 모두 가림 처리) |
| `og.jpg` | 카카오톡·문자로 링크 공유할 때 뜨는 미리보기 이미지 |
| `sitemap.xml`, `robots.txt` | 검색엔진 수집용 |
| `CNAME` | 개인 도메인을 연결했을 때만 생성됩니다 |
| `.nojekyll` | GitHub Pages가 파일을 그대로 서비스하도록 지정 |

## 검색 최적화 현황

- 페이지마다 `title` · `description` · Open Graph 미리보기 설정
- 메인 `h1`에 "가양역 헬스장 · 24시간 운영" 키워드 포함
- 구조화 데이터(JSON-LD)
  - `HealthClub` — 주소, 전화, 운영시간, **매월 둘째 주 일요일 정기 휴관일(향후 8회분 자동 계산)**, 편의시설, 일일권 가격
  - `FAQPage` — Q&A 10문항이 그대로 들어가 검색 결과에 바로 노출될 수 있음
  - `Person` — 트레이너 페이지마다 이름·전문 분야·블로그 연결

## 게시 설정

저장소 **Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)`**

## 개인 도메인 연결

`site.config.json`의 `domain` 한 줄만 채우고 다시 빌드하면 `CNAME` 파일, canonical 주소, sitemap, 구조화 데이터 주소가 한꺼번에 바뀝니다.

```json
{ "domain": "example.com" }
```

그다음 도메인 구입처(가비아·후이즈 등) DNS에 아래 레코드를 넣습니다.

| 종류 | 호스트 | 값 |
| --- | --- | --- |
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | `1986-fitness-gayang.github.io` |

마지막으로 저장소 **Settings → Pages → Custom domain** 에 도메인을 입력해 저장하고, 인증이 끝나면 **Enforce HTTPS** 를 체크합니다. (보통 10분~1시간)

## 검색엔진 등록

소유확인 코드를 받으면 `site.config.json`에 넣고 다시 빌드하면 됩니다. 코드만 넣으면 메타 태그가 자동으로 삽입됩니다.

```json
{ "naverVerify": "네이버 서치어드바이저 코드", "googleVerify": "구글 서치콘솔 코드" }
```

- 네이버 서치어드바이저 <https://searchadvisor.naver.com> → 사이트 등록 → 소유확인(HTML 태그) → 수집 요청 + 사이트맵 제출
- 구글 서치콘솔 <https://search.google.com/search-console> → URL 접두어 → 소유확인 → 사이트맵 제출
- 네이버 스마트플레이스 → 업체정보 → **홈페이지** 항목에 위 주소 등록

## 페이지 수정

본문·사진·영상은 Claude Design 캔버스에서 수정한 뒤 다시 내보냅니다. 직접 고칠 때는 해당 HTML 파일을 열어 수정하면 되고, 레이아웃은 1440px 고정이라 PC와 모바일이 동일하게 보입니다.

## 문의

02-2658-5607 · 서울특별시 강서구 양천로 500 노블리움오피스텔 307·308호 3층
