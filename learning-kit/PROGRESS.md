# PROGRESS — единый источник правды о переводе и обучении

Обновляется в каждой сессии. Коуч (`lesson-coach`) читает только этот файл для определения состояния.

## Статусы перевода

- `TODO` — файл ещё не переведён (en-версия доступна).
- `translated` — русский перевод готов в `docs/ru/`.
- `done` — урок пройден учеником (wizard завершён, артефакт заполнен).
- `missing-in-en` — файла нет в en-версии.
- `zh-delta` — в zh-оригинале есть материал сверх en-версии; переводится в существующий ru-файл (ветка `ru-zh`).

## Сводка (дата: 2026-09-04)

| Раздел | Переведено / Всего | %
|---|---|---|
| Basic | 47 / 47 | 100% |
| Advanced | 101 / 101 | 100% ✅
| Articles | 48 / 48 | 100% ✅
| Practice | 5 / 5 | 100% ✅

ПЕРЕВОД ЗАВЕРШЁН ✅ (2026-09-16). Все разделы переведены на 100%: Basic 47/47; Advanced 101/101; Articles 48/48 (index + 01-core-concepts 11 + 02-technical-architecture 8 + 03-toolchain-frameworks 8 + 04-engineering-practices 13 + 05-security-compliance 3 + 06-business-trends 5); Practice 5/5. Итог: 201/201 файл.

## zh-материал — ветка `ru-zh` (расширение скоупа, 2026-09-04)

Задача: перевести китайский материал проекта, которого нет в en-зеркале, БЕЗ дублирования — единое зеркало `docs/ru/`, дельты zh→en вшиваются в существующие ru-файлы. Ветка `ru-zh` (от `ru`), пуш на fork (`Levkippdev/vibe-vibe`); слияние в `ru` — после завершения скоупа. Правила: en/zh не изменяем никогда; в начале каждой сессии пересчитывать скан zh↔en (если upstream переведёт материал в en — дельта обнулится сама).

Пакеты: P0 zh-only → P1 индексы Articles + лёгкие дельты → P2 тяжёлые статьи (complete-guide-to-building-skills-for-claude и др.).

| Файл | Тип | Статус | Дата |
|---|---|---|---|
| Practice/full-stack-21-day-thinking-habit-game.md | zh-only (321 стр.) | translated ✅ | 2026-09-04 |
| deployment/index.md | zh-only (231 стр.; вне сайдбара, как у upstream) | translated ✅ | 2026-09-04 |
| ru/Practice/index.md | +строка статьи | обновлён ✅ | 2026-09-04 |
| Articles/01-core-concepts/index.md | zh-delta (zh 164 / en 35) | translated ✅ | 2026-09-04 |
| Articles/02-technical-architecture/index.md | zh-delta (zh 119 / en 32) | translated ✅ | 2026-09-04 |
| Articles/03-toolchain-frameworks/index.md | zh-delta (zh 119 / en 32) | translated ✅ | 2026-09-04 |
| Articles/04-engineering-practices/index.md | zh-delta (zh 195 / en 37) | translated ✅ | 2026-09-04 |
| Articles/05-security-compliance/index.md | zh-delta (zh 45 / en 25) | translated ✅ | 2026-09-04 |
| Articles/06-business-trends/index.md | zh-delta (zh 63 / en 28) | translated ✅ | 2026-09-04 |
| Articles/03-.../complete-guide-to-building-skills-for-claude.md | zh-delta (zh 1326 / en 313) | translated ✅ (перестроен по zh, 1373 строк: кухонная аналогия, категории, метрики, шаблон SKILL.md, тесты, дистрибуция/API, 5 паттернов, траблшутинг, приложения) | 2026-09-04 |
| Articles/01-.../what-are-ai-agents-why-do-they-matter.md | zh-delta (zh 426 / en 206) | translated ✅ (перестроен по zh, 422 строки: 11 картинок, «почему в восторге», архитектурные паттерны, браузерные агенты, кейсы) | 2026-09-04 |
| Articles/04-.../leading-effective-engineering-teams-in-the-age-of-genai.md | zh-delta (zh 392 / en 152) | translated ✅ (приложение «полная версия оригинала») | 2026-09-04 |
| Articles/04-.../vercel-aeo-tracking.md | zh-delta (zh 337 / en 145; zh и en — разные статьи!) | translated ✅ (перестроен по zh: реальный кейс — 6-шаговый lifecycle, agent-as-config, 4 фазы нормализации; en-концепция — приложением) | 2026-09-04 |
| Articles/01-.../vibe-coding-revolution-or-reckless-abandon.md | zh-delta (zh 266 / en 121) | translated ✅ (перестроен по zh, 249 строк: HN-цитаты, security/maintainability, prototype-vs-production, карьерные импликации; zh-артефакты дублей вычищены) | 2026-09-04 |
| Articles/04-.../ai-code-review-implementation.md | zh-delta (zh 259 / en 119) | translated ✅ (перестроен по zh, en-only — в приложении) | 2026-09-04 |
| Articles/05-.../ai-agents-threats-and-mitigations.md | zh-delta (zh 192 / en 96) | translated ✅ (перестроен по zh: research-кейс CrewAI/AutoGen, 9 сценариев таблицей, 6 стратегий; en-таксономия — приложением) | 2026-09-04 |
| Articles/01-.../coding-agents-101.md | zh-delta (zh 317 / en 196) | translated ✅ (вшита дельта: экосистема, leverage-expertise, все примеры, playbooks, planning modes, env-детали) | 2026-09-04 |
| Articles/02-.../how-claude-code-works.md | zh-delta (zh 280 / en 187) | translated ✅ (перестроен по zh, 314 строк: 4 паттерна с реальными цитатами промптов, Bash tool, открытые вопросы; en-only — приложением) | 2026-09-04 |
| Articles/02-.../mcp-what-it-is-and-why-it-matters.md | zh-delta (zh 270 / en 181) | translated ✅ (перестроен по zh, 268 строк: ELI5+Blender, история, архитектура, кейсы Figma/Unity/Zapier, старт, лимиты, будущее) | 2026-09-04 |
| Articles/04-.../how-to-write-a-good-spec-for-ai-agents.md | zh-delta (zh 264 / en 170) | translated ✅ (перестроен по zh, 257 строк: plan mode, 6 доменов GitHub, Spec Kit 4 фазы, sub-agents, LLM-as-judge, анти-паттерны) | 2026-09-04 |
| Articles/03-.../how-to-write-good-spec-for-ai-agents.md | zh-delta (zh 254 / en 187) | translated ✅ (проверено: ru уже выше en; дельта закрыта ранее в rebuild 04-версии) | 2026-09-04 |
| Articles/03-.../why-i-use-cline-for-ai-engineering.md | zh-delta (zh 324 / en 225; ru 123 — короче даже en!) | translated ✅ (перестроен по zh, 321 строка: 7 картинок, DeepSeek-R1+Sonnet, checkpoints, Computer Use, Plan/Act, MCP marketplace, сравнение конкурентов) | 2026-09-04 |
| Articles/04-.../video-generation-with-ai-gateway.md | zh-delta (zh 266 / en 186) | translated ✅ (перестроен по zh, 263 строки: 4 типа генерации, 6 код-примеров, first-last frame, r2v) | 2026-09-04 |
| Articles/01-.../the-factory-model-...md | zh-delta (zh 186 / en 128) | translated ✅ (вшито: Booch third age, Cursor quotes, секция «что не изменилось», TDD-шорткат, история ассемблер→C) | 2026-09-04 |
| Articles/01-.../world-class-agent-engineer.md | zh-delta (zh 209 / en 172) | translated ✅ (вшит полный sycophancy-кейс, секция «Как понять, что работает», детали) | 2026-09-04 |
| Articles/03-.../agents-md-vs-skills.md | zh-delta (zh 242 / en 226) | translated ✅ (вшиты zh-секции: хрупкость формулировок, eval'ы, интуиция, результаты, компрессия, codemod, уроки) | 2026-09-04 |
| Articles/04-.../my-llm-coding-workflow-going-into-2026.md | zh-delta (zh 180 / en 113) | translated ✅ (перестроен по zh, 194 строки: 8 секций полностью; en-only паттерны — приложением) | 2026-09-04 |
| Articles/05-.../security-boundaries-in-agentic-architectures.md | zh-delta (zh 159 / en 104) | translated ✅ (перестроен по zh, 182 строки: log-injection demo, 4 участника, 4 архитектуры, 4 картинки; en-only — приложением) | 2026-09-04 |
| Articles/06-.../the-next-two-years-of-software-engineering.md | zh-delta (zh 168 / en 103) | translated ✅ (перестроен по zh, 194 строки: 5 вопросов с данными и советами; en-only — приложением) | 2026-09-04 |
| Articles/04-.../stop-using-init-for-agents.md | zh-delta (zh 191 / en 125) | translated ✅ (перестроен по zh, 225 строк: Lulla/ETH, розовый слон, 3-слойная архитектура, автооптимизация; en-only — приложением) | 2026-09-04 |
| Articles/04-.../ai-writes-code-faster-....md | zh-delta (zh 153 / en 113) | translated ✅ (перестроен по zh, 168 строк: метрики PR+18%/24%/30%, security-статы, PR-контракт; en-only — приложением) | 2026-09-04 |
| Articles/01-.../specs-are-the-new-source-code.md | zh-delta (zh 160 / en 119) | translated ✅ (вшито: bottleneck-интро, Danny-кейс с цитатой, гейткипинг, PM-аутлук) | 2026-09-04 |
| Articles/01-.../vibe-coding-is-not-an-excuse-....md | zh-delta (zh 147 / en 121) | translated ✅ (вшито: 3 картинки, карточный домик-link, правила 2-7 расширены, кейсы детализированы, F1-школьный автобус) | 2026-09-04 |
| Articles/04-.../react-best-practices.md | zh-delta (zh 158 / en 132) | translated ✅ (перестроен по zh, 181 строка: приоритизация, async-пример, продакшн-кейсы, Agent Skills) | 2026-09-04 |
| Articles/03-.../ai-driven-prototyping-....md | zh-delta (zh 187 / en 164) | translated ✅ (вшито: 10 картинок, фичи-блоки v0/Bolt/Lovable, общие вызовы) | 2026-09-04 |
| Articles/06-.../keeping-community-human-....md | zh-delta (zh 146 / en 123) | translated ✅ (перестроен по zh, 160 строк: Guardian, c0, метрики 281/4716, эволюция промптов; en-only — приложением) | 2026-09-04 |
| Articles/04-.../beyond-the-70-....md | zh-delta (zh 154 / en 134) | translated ✅ (добавлено приложение: 7 навыков, сеньоры CHOP, джуны no-AI days, consumption-to-creation) | 2026-09-04 |
| Articles/index.md | zh-delta (zh 52 / en 35) | translated ✅ (перестроен по zh: навигация по вопросам решений + «кому читать») | 2026-09-04 |
| Articles/01-.../what-you-need-to-know-about-vibe-coding.md | zh-delta (zh 187 / en 172) | translated ✅ (восстановлены 4 картинки) | 2026-09-04 |

**Вывод сессии 2026-09-04:** en-версии Articles — самостоятельные сокращённые редакции zh (не подмножества, местами другой контент: пример — vercel-aeo-tracking, ai-code-review). Рабочая стратегия: ru перестраивать по структуре zh (полный перевод), уникальные en-only блоки сохранять в конце разделом «## Дополнительно (из en-версии)». Субагенты большие переводы (~200+ строк выхода) не вытягивают — падают без записи; переводить в основной сессии вручную. Мелкие дельты — точечным вшиванием через edit.

**Вывод сессии 2026-09-04 (третий блок, завершение ru-zh):** zh-материал Articles ЗАВЕРШЁН полностью: все 40+ позиций таблицы ✅. Мелкие дельты (12–67 строк) закрывались точечным вшиванием (factory-model, specs, vibe-coding-excuse, prototyping, what-you-need-to-know) или приложением (beyond-the-70, threats). Картинки восстанавливать обязательно — zh вставляет их чаще ru/en (prototyping 10, what-you-need-to-know 4, vibe-coding-excuse 3).

**Второй блок сессии:** закрыты ВСЕ тяжёлые дельты (13 файлов, каждый 190–1373 строк): skills-guide, what-are-ai-agents, vercel-aeo, vibe-coding-revolution, coding-agents-101, how-claude-code-works, mcp, spec-good (04), cline, video-generation, threats, my-llm-workflow + Articles/index.md. Техника подтверждена: полный rebuild по zh + «Дополнительно (из en-версии)» для уникального en-контента; для параллельных структур (coding-agents-101) — точечное вшивание. zh-оригиналы содержат артефакты («обглупления»: дублированные/искажённые абзацы, 汉字-вставки) — переводить по смыслу, мусор не переносить; проверка grep '[一-鿿]' после каждого файла обязательна (ловились 适配ация/声明/产出/核心/叠加/前提/看重/环境).

Вне скоупа (backlog, как и прежде): zh-UI в 116 Vue-компонентах темы (~3600 строк), root-локаль zh в config.mts/modules, `Basic-old/`, `demos/`, `zh/index.md`.

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
| 02-mindset/index.md | translated | 2026-09-01 | — |
| 02-mindset/2.1-thinking-upgrade.md | translated | 2026-09-01 | pending |
| 02-mindset/2.2-inversion-thinking.md | translated | 2026-09-01 | pending |
| 02-mindset/2.3-subtraction-thinking.md | translated | 2026-09-01 | pending |
| 02-mindset/2.4-story-thinking.md | translated | 2026-09-01 | pending |
| 03-technique/index.md | translated | 2026-09-01 | — |
| 03-technique/3.1-prompt-basics.md | translated | 2026-09-01 | pending |
| 03-technique/3.2-structured-frameworks.md | translated | 2026-09-01 | pending |
| 03-technique/3.3-advanced-techniques.md | translated | 2026-09-01 | pending |
| 03-technique/3.4-first-prd.md | translated | 2026-09-01 | pending |
| 04-practice-0-to-1/index.md | translated | 2026-09-01 | — |
| 04-practice-0-to-1/4.1-before-start.md | translated | 2026-09-01 | pending |
| 04-practice-0-to-1/4.2-build-page.md | translated | 2026-09-01 | pending |
| 04-practice-0-to-1/4.3-core-features.md | translated | 2026-09-01 | pending |
| 04-practice-0-to-1/4.4-data-storage.md | translated | 2026-09-01 | pending |
| 05-advanced/index.md | translated | 2026-09-01 | — |
| 05-advanced/5.1-version-control.md | translated | 2026-09-01 | pending |
| 05-advanced/5.2-deployment.md | translated | 2026-09-01 | pending |
| 05-advanced/5.3-security.md | translated | 2026-09-01 | pending |
| 05-advanced/5.4-iteration.md | translated | 2026-09-01 | pending |
| 06-launch/index.md | translated | 2026-09-01 | — |
| 06-launch/6.1-preflight.md | translated | 2026-09-01 | pending |
| 06-launch/6.2-deploy.md | translated | 2026-09-01 | pending |
| 06-launch/6.3-feedback.md | translated | 2026-09-01 | pending |
| 06-launch/6.4-wrap-up.md | translated | 2026-09-01 | pending |
| 99-appendix/index.md | translated | 2026-09-01 | — |
| 99-appendix/a-prompt-cheatsheet.md | translated | 2026-09-01 | — |
| 99-appendix/b-errors-and-asking-ai.md | translated | 2026-09-01 | — |
| 99-appendix/c-ui-cheatsheet.md | translated | 2026-09-01 | — |
| 99-appendix/d-git-minimal-card.md | translated | 2026-09-01 | — |
| 99-appendix/e-api-key-env-security.md | translated | 2026-09-01 | — |
| 99-appendix/f-vibe-coding-can-and-cannot.md | translated | 2026-09-01 | — |
| 99-appendix/g-advanced-jump-map.md | translated | 2026-09-01 | — |
| 100-epilogue/index.md | translated | 2026-09-01 | — |
| 101-next-part/index.md | translated | 2026-09-01 | — |
| 101-next-part/preview-advanced-content.md | translated | 2026-09-01 | — |

## Advanced — 101 файл (101/101 translated) ✅

| Глава (docs/ru/Advanced/...) | Статус | Дата |
|---|---|---|
| 01-environment-setup/ (10 файлов: index, 00–08) | translated | 2026-09-01 |
| 02-ai-tuning-guide/ (7 файлов: index, 00–05) | translated | 2026-09-02 |
| 03-prd-doc-driven/ (6 файлов: index, 00–04) | translated | 2026-09-02 |
| 04-dev-fundamentals/ (11 файлов: index, 00–09) | translated | 2026-09-03 |
| 05-ui-ux/ (7 файлов: index, 01–06) | translated | 2026-09-04 |
| 06-data-persistence-database/ (6 файлов: index, 00–03, 05; в EN нет 04) | translated | 2026-09-05 |
| 07-backend-api/ (5 файлов: index, 00–03) | translated | 2026-09-06 |
| 08-auth-security/ (7 файлов: index, 00–05) | translated | 2026-09-07 |
| 09-testing-automation/ (4 файла: index, 01–03) | translated | 2026-09-08 |
| 10-localhost-public-access/ (3 файла: index, 01–02) | translated | 2026-09-09 |
| 11-git-collaboration/ (4 файла: index, 01–03) | translated | 2026-09-10 |
| 12-serverless-deploy-cicd/ (5 файлов: index, 01–04) | translated | 2026-09-11 |
| 13-domain-dns/ (3 файла: index, 01–02) | translated | 2026-09-12 |
| 14-vps-ops-deploy/ (9 файлов: index, 01–05, 03-1–03-4) | translated | 2026-09-13 |
| 15-seo-analytics/ (5 файлов: index, 01–04) | translated | 2026-09-14 |
| 16-user-feedback-iteration/ (5 файлов: index, 01–04) | translated | 2026-09-15 |
| happy-coder.md, web-ide.md, 99-next-level/, index.md (4 файла) | translated | 2026-09-16 |

Перевод — по одной главе за сессию. Steps-файлы для Advanced опциональны (wizard — для Basic).

## Articles — 48 файлов (опциональный приоритет; 12/48 translated)

- index.md — translated (2026-09-16)
- 01-core-concepts/ (10 файлов + index) — translated ✅ (2026-09-16): what-are-ai-agents-why-do-they-matter, what-you-need-to-know-about-vibe-coding, agentic-engineering, the-factory-model-how-coding-agents-changed-software-engineering, world-class-agent-engineer, specs-are-the-new-source-code, coding-agents-101, how-we-vibe-code-at-faang, vibe-coding-revolution-or-reckless-abandon, vibe-coding-is-not-an-excuse-for-low-quality-work
- 02-technical-architecture/ (8 файлов) — translated ✅ (2026-09-16): index, how-claude-code-works, mcp-what-it-is-and-why-it-matters, build-agents-with-filesystems-and-bash, testing-bash-vs-sql, self-improving-coding-agents, multi-agent-systems-ai-native-engineering, nvidia-ai-5-layer-cake
- 03-toolchain-frameworks/ (8 файлов) — translated ✅ (2026-09-16): index, claude-code-swarms, how-to-write-good-spec-for-ai-agents, ai-driven-prototyping-v0-bolt-and-lovable-compared, why-i-use-cline-for-ai-engineering, agents-md-vs-skills, complete-guide-to-building-skills-for-claude, we-removed-80-percent-tools
- 04-engineering-practices/ (13 файлов) — translated ✅ (2026-09-16): index, ai-writes-code-faster-your-job-is-to-prove-it-works, my-llm-coding-workflow-going-into-2026, avoiding-skill-atrophy-in-the-age-of-ai, ai-code-review-implementation, stop-using-init-for-agents, react-best-practices, beyond-the-70-maximizing-the-human-30-of-ai-assisted-coding, vercel-aeo-tracking, leading-effective-engineering-teams-in-the-age-of-genai, your-ai-coding-agents-need-a-manager, how-to-write-a-good-spec-for-ai-agents, video-generation-with-ai-gateway
- 05-security-compliance/ (3 файла) — translated ✅ (2026-09-16): index, ai-agents-threats-and-mitigations, security-boundaries-in-agentic-architectures
- 06-business-trends/ (4 файла) — translated ✅ (2026-09-16): index, the-next-two-years-of-software-engineering, how-openevidence-built-healthcare-ai-physicians-trust, keeping-community-human-while-scaling-with-agents

Перевод после Advanced.

## Practice — 6 файлов (у zh на 1 больше; zh-only статья переведена на ветке `ru-zh`, см. секцию «zh-материал»)

- ai-canvas-vibecoding-journey.md — translated (2026-09-16)
- ai-picture-book-generator.md — translated (2026-09-16)
- ai-resume-saas.md — translated (2026-09-16)
- full-stack-21-day-thinking-habit-game.md — translated ✅ (2026-09-04, ветка `ru-zh`; zh-only, в en-версии файла нет)
- index.md — translated (2026-09-16; на `ru-zh` добавлена строка 21-дневной игры)
- vibe-coding-methodology.md — translated (2026-09-16)

## Примечания

- Steps-файлы визарда: глава 0 — `00-preface.md`; глава 1 — `01-1...01-4` (по уроку); главы 2–6 — единые файлы: `02-local.md`, `03-style.md`, `04-content.md`, `05-twin.md`, `06-launch.md`.
- Vue-компоненты в Advanced-уроках при переводе сохраняются как есть; их китайский UI — backlog.
- `Basic-old/` (224 файла) и zh-контент вне перевода.
- Запуск dev-server: `pnpm dev` в корне репо (ветка `ru`).
