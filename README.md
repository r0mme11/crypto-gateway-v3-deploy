# Docker

LOGIN: gitlab+deploy-token-1330364
PASSWORd: s-Z2tAonTm7teesC9qHK

git clone https://gitlab.com/timeformoney/moneywheel/docker.git



# Migrations (Prisma)

The API uses Prisma 6. `DATABASE_URL` and `MASTER_KEK` must be set (see
`.common.env`). Migrations are NOT auto-run on boot — apply them before
starting the services, e.g. via a one-off container against the `api` image:

## Apply migrations + seed (once, against a running db)
docker compose -f docker-compose-local.yml run --rm api npx prisma migrate deploy
docker compose -f docker-compose-local.yml run --rm api npx prisma db seed

## Create a new migration (in the api repo, against a dev db)
npm run prisma:migrate:dev -- --name <migration-name>
