# Public Figures Archive

주요 인사들의 공개 일정, 발언, 진행 중인 일, 주요 이슈, 그리고 주간/월간/분기/반기 통계 보고서를 저장하는 archive repository입니다.

이 repo는 n8n/Hermes 기반 콘텐츠 자동화 MVP의 네 번째 archive target입니다. 현재는 scaffold 상태이며, 반복 실행과 live delivery는 사용자 명시 승인 전까지 비활성으로 둡니다.

## Intended flow

1. n8n/deterministic scripts read person-specific source registries.
2. RSS/API/official sources are checked first.
3. URL-specific full-text fetch is used only when needed.
4. Events are normalized and deduplicated.
5. Hermes summarizes, separates facts/claims/quotes, and creates reports only when new events exist.
6. Daily/weekly/monthly/quarterly/semiannual outputs are saved here.
7. Live delivery is enabled only after explicit approval.

## Directory layout

- `sources/`: 인물별 source registry, feed/API/crawl placeholder.
- `raw/`: 원본 수집 snapshot 또는 source metadata.
- `processed/`: deduped/normalized event records.
- `outputs/`: 일일 brief, intermediate Hermes outputs.
- `reports/`: 주간/월간/분기/반기 보고서.
- `stats/`: 인물별/주제별 통계 JSON/CSV.
- `logs/`: run manifest, quality gate log, publication/delivery log.

## Safety gates

- `recurring_enabled`: false by default.
- `live_delivery_enabled`: false by default.
- Paid Kakao delivery is not used in the MVP stage.
- Telegram/Discord/Slack test delivery can be added later, but recurring delivery requires explicit approval.
