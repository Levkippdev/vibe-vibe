# PROGRESS — единый источник правды о переводе и обучении

Обновляется в каждой сессии. Коуч (`lesson-coach`) читает только этот файл для определения состояния.

## Статусы перевода

- `TODO` — файл ещё не переведён (en-версия доступна).
- `translated` — русский перевод готов в `docs/ru/`.
- `done` — урок пройден учеником (wizard завершён, артефакт заполнен).
- `missing-in-en` — файла нет в en-версии.

## Сводка (дата: 2026-08-31)

| Раздел | Переведено / Всего | %
|---|---|---|
| Basic | 11 / 47 | 23%
| Advanced | 0 / 101 | 0%
| Articles | 0 / 48 | 0%
| Practice | 0 / 5 | 0%

Курсор следующего пакета: `Basic/02-mindset/` (5 файлов).

## Basic — карта уроков

| Путь (docs/ru/Basic/...) | Статус | Дата | Урок (wizard) |
|---|---|---|---|
| index.md | translated | 2026-08-31 | — |
| 00-preface/index.md | translated | 2026-08-31 | pending |
| 00-preface/0.1-start-here.md | translated | 2026-08-31 | pending |
| 00-preface/0.2-what-you-will-build.md | translated | 2026-08-31 | pending |
| 00-preface/0.3-who-this-is-for.md | translated | 2026-08-31 | pending |
| 00-preface/0.4-how-to-learn.md | translated | 2026-08-31 | pending |
| 01-awakening/index.md | translated | 2026-08-31 | pending |
| 01-awakening/1.1-coder-to-commander.md | translated | 2026-08-31 | pending |
| 01-awakening/1.2-breaking-myths.md | translated | 2026-08-31 | pending |
| 01-awakening/1.3-tools-guide.md | translated | 2026-08-31 | pending |
| 01-awakening/1.4-vibe-vs-spec.md | translated | 2026-08-31 | pending |
| 02-mindset/index.md | TODO | — | — |
| 02-mindset/2.1-thinking-upgrade.md | TODO | — | — |
| 02-mindset/2.2-inversion-thinking.md | TODO | — | — |
| 02-mindset/2.3-subtraction-thinking.md | TODO | — | — |
| 02-mindset/2.4-story-thinking.md | TODO | — | — |
| 03-technique/index.md | TODO | — | — |
| 03-technique/3.1-prompt-basics.md | TODO | — | — |
| 03-technique/3.2-structured-frameworks.md | TODO | — | — |
| 03-technique/3.3-advanced-techniques.md | TODO | — | — |
| 03-technique/3.4-first-prd.md | TODO | — | — |
| 04-practice-0-to-1/index.md | TODO | — | — |
| 04-practice-0-to-1/4.1-before-start.md | TODO | — | — |
| 04-practice-0-to-1/4.2-build-page.md | TODO | — | — |
| 04-practice-0-to-1/4.3-core-features.md | TODO | — | — |
| 04-practice-0-to-1/4.4-data-storage.md | TODO | — | — |
| 05-advanced/index.md | TODO | — | — |
| 05-advanced/5.1-version-control.md | TODO | — | — |
| 05-advanced/5.2-deployment.md | TODO | — | — |
| 05-advanced/5.3-security.md | TODO | — | — |
| 05-advanced/5.4-iteration.md | TODO | — | — |
| 06-launch/index.md | TODO | — | — |
| 06-launch/6.1-preflight.md | TODO | — | — |
| 06-launch/6.2-deploy.md | TODO | — | — |
| 06-launch/6.3-feedback.md | TODO | — | — |
| 06-launch/6.4-wrap-up.md | TODO | — | — |
| 99-appendix/index.md | TODO | — | — |
| 99-appendix/a-prompt-cheatsheet.md | TODO | — | — |
| 99-appendix/b-errors-and-asking-ai.md | TODO | — | — |
| 99-appendix/c-ui-cheatsheet.md | TODO | — | — |
| 99-appendix/d-git-minimal-card.md | TODO | — | — |
| 99-appendix/e-api-key-env-security.md | TODO | — | — |
| 99-appendix/f-vibe-coding-can-and-cannot.md | TODO | — | — |
| 99-appendix/g-advanced-jump-map.md | TODO | — | — |
| 100-epilogue/index.md | TODO | — | — |
| 101-next-part/index.md | TODO | — | — |
| 101-next-part/preview-advanced-content.md | TODO | — | — |

## Advanced — 101 файл (все TODO)

Все файлы перечислены в `docs/en/Advanced/` (16 глав + happy-coder + web-ide + 99-next-level). Перевод — по одной главе за сессию после завершения Basic.

## Articles — 48 файлов (все TODO, опциональный приоритет)

Перевод после Advanced.

## Practice — 5 файлов en (у zh на 1 больше; расхождение помечено missing-in-en)

- ai-canvas-vibecoding-journey.md — TODO
- ai-picture-book-generator.md — TODO
- ai-resume-saas.md — TODO
- full-stack-21-day-thinking-habit-game.md — TODO
- index.md — TODO
- vibe-coding-methodology.md — TODO

## Примечания

- Vue-компоненты в Advanced-уроках при переводе сохраняются как есть; их китайский UI — backlog.
- `Basic-old/` (224 файла) и zh-контент вне перевода.
- Запуск dev-server: `pnpm dev` в корне репо (ветка `ru`).
