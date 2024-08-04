# .github/workflows/api-ci.yml  

<!-- name: API CI

on:
  push:
    branches: ['*']
  pull_request:
    branches: [main, master]

jobs:
  e2e:
    runs-on: ubuntu-latest
    container:
      image: node:16

    services:
      postgres-e2e:
        image: postgres:13
        ports:
          - 5433:5432
        env:
          POSTGRES_DB: db_e2e
          POSTGRES_USER: e2e
          POSTGRES_PASSWORD: e2e123

    steps:
      - name: Checkout
        uses: actions/checkout@v3
      - name: Install
        run: pnpm ci
      - name: run e2e
        run: pnpm run e2e:ci
        env:
          PORT: 3000
          DATABASE_URL: postgres://e2e:e2e123@postgres-e2e:5433/db_e2e
          API_KEY: 79823
          JWT_SECRET: my_cat_1212
          SMTP_EMAIL: your@email.com
          SMTP_PASSWORD: password-email -->