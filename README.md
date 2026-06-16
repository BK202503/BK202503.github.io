# bk202503.github.io

김빌(Bill Kim)의 오픈소스(OSS) 활동 랜딩 페이지.

- Site: https://bk202503.github.io/
- Blog: https://devbilllab.tistory.com/

## 구성

순수 HTML/CSS. 빌드 단계 없이 GitHub Pages가 그대로 서빙합니다.

```
index.html                                메인 랜딩
style.css                                 공통 스타일
robots.txt                                크롤러 가이드 (sitemap 지정)
sitemap.xml                               전체 URL 목록 (hreflang ko/en)
libraries/
  bk-spring-idempotent.html               Stripe-style @Idempotent for Spring Boot
  bk-spring-saga.html                     Coroutine-native Saga orchestrator
  bk-spring-outbox.html                   Transactional Outbox for Spring Boot
contributions/
  apache-kafka.html                       Kafka Connect ByteBuffer 시리즈
  spring-kafka.html                       suspend @KafkaListener retry 회귀 수정
  spring-modulith.html                    JpaEventPublicationAdapter#getStatus 영속 상태
  spring-ai.html                          streaming observation stop order 회귀 테스트
  infinispan.html                         PMD CPD GitHub workflow
projects/
  korea-cafe.html                         Naver Local Search 카페 메타데이터 파이프라인
```

각 서브페이지에 고유 `<title>` / `<meta name="description">` / canonical URL / hreflang / JSON-LD(BreadcrumbList + SoftwareSourceCode/TechArticle)를 박아 SEO 시그널을 페이지별로 분리.

## 작업 흐름

브랜치 → PR → 머지가 기본. `main`에 직접 푸시하지 않음.

```sh
git checkout -b feat/<scope>
# 편집 후
git add -A && git commit -m "..."
git push -u origin feat/<scope>
gh pr create --base main --title "..." --body "..."
gh pr merge <number> --merge --delete-branch
```

자세한 룰과 PII / 레포 visibility 체크리스트는 `CLAUDE.md`.

## 로컬 미리보기

```sh
python3 -m http.server 8080
# → http://localhost:8080
```
