# Docker

LOGIN: gitlab+deploy-token-1330364
PASSWORd: s-Z2tAonTm7teesC9qHK

git clone https://gitlab.com/timeformoney/moneywheel/docker.git



# Migrations

## Generate migrations
npm run  typeorm migration:generate -- -d libs/database/src/data.source.ts libs/database/src/migrations/initial-migration
