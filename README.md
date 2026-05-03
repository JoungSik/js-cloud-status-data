# js-cloud-status-data

JS Cloud status 페이지의 측정 데이터 저장소. 사이트 코드는 별도 private repo([js-cloud-status](https://github.com/JoungSik/js-cloud-status))에서 관리.

- 측정 주기: 60분 (GitHub Actions cron)
- 자동 갱신: status repo의 collect.yml workflow가 push
- 사이트 fetch URL: GitHub raw (`https://raw.githubusercontent.com/JoungSik/js-cloud-status-data/main/data.json`, 5분 캐시)
- 보관 기간: 365일 (자동 삭제)

## 파일

- `data.json` — 사전 집계 (사이트가 fetch). endpoint 등 민감 정보 미포함
- `data/checks/YYYY-MM-DD.ndjson` — 일자별 측정 결과 누적

수동 편집 금지. 모든 변경은 GitHub Actions가 자동 수행.
