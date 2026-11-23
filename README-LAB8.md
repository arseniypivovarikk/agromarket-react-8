# AgroMarket — Лабораторная работа №8

## Что реализовано
- GitHub Flow: ветка `feature/api-tests` и Conventional Commits (описаны в памятке).
- Express вынесен в `agromarket-server/app.js`, запуск в `server.js`.
- Vitest + Supertest: health, каталог, регистрация/вход, `/api/auth/me`, роли и заявки.
- Unit-тесты middleware `requireAuth` / `requireRole`.
- `npm test`, `npm run test:watch`, `npm run coverage`.
- GitHub Actions для API тестов и React build.
- React API URL задаётся через `VITE_API_URL` в `.env.development`.

> В исходном проекте ЛР7 используется JSON-хранилище, а не PostgreSQL. Поэтому CI здесь запускает тесты без PostgreSQL, на изолированных JSON-файлах. Это адаптация под имеющийся проект; если преподаватель требует именно PostgreSQL, потребуется перенос серверного хранилища.

## Запуск тестов
```bash
cd agromarket-server
cp .env.test.example .env.test
n npm install
npm test
npm run coverage
```

## Git workflow (для ручного выполнения)
```bash
git switch main
git pull
git switch -c feature/api-tests
git add .
git commit -m "test: add API and middleware tests"
git push -u origin feature/api-tests
```
Затем GitHub → Pull requests → New pull request, base `main`, compare `feature/api-tests`. В PR запросите review напарника, дождитесь CI и выполните merge.

## Conventional Commits
`feat`, `fix`, `test`, `refactor`, `docs`, `ci`, `chore` — типы сообщений коммитов.

## О тестовом окружении
Тестовые файлы `data/db.test.json` и `data/users.test.json` создаются отдельно и игнорируются Git. `.env.test` тоже не добавляйте в репозиторий.

## ЛР8 — ответы (заполнить после фактического запуска)
- Какие тесты упали при удалении `requireRole`?
- Coverage Lines и непокрытая строка: ...
- Разница unit и integration тестов: ...
- Code-review: ...
- ИИ: ...
