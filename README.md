# React_Project

Практическая работа: автоматизация деплоя React-приложения на GitHub Pages с помощью GitHub Actions.

## Что реализовано

- Создан workflow: `.github/workflows/deploy.yml`
- Настроен CI pipeline:
  - установка зависимостей (`npm install`)
  - проверка линтером (`npm run lint`)
  - сборка проекта (`npm run build`)
- Настроен CD:
  - автоматический деплой на GitHub Pages после успешной сборки
  - ручной запуск через `workflow_dispatch` (кнопка `Run workflow` в Actions)
- Деплой публикации выполняется в ветку `gh-pages`

## Триггеры workflow

- `push` в `main`
- `pull_request` в `main`
- ручной запуск (`workflow_dispatch`)

## Скрипты проекта

- `npm run lint` - запуск линтера
- `npm run build` - production build
- `npm run deploy` - деплой build в ветку `gh-pages`

## GitHub Pages

- Source: `Deploy from a branch`
- Branch: `gh-pages`
- Folder: `/ (root)`

Сайт:
[https://atamurat2004.github.io/React_Project/](https://atamurat2004.github.io/React_Project/)

## Как проверить

1. Сделать изменение в `src/App.js`
2. Выполнить:
   - `git add .`
   - `git commit -m "test ci/cd"`
   - `git push origin main`
3. Открыть вкладку `Actions` и убедиться, что workflow `Deploy` завершился со статусом `Success`
4. Проверить обновление на сайте GitHub Pages
