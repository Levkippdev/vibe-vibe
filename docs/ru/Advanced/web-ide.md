---
title: "Облачное dev-окружение за 5 минут"
description: "Гайд новичка по cloud-native разработке на CNB"
order: 1
---

# Достаточно браузера — и всё coding-окружение готово

Вам надоели:

- Дни на настройку dev-окружения?
- Компьютер, который не тянет Docker?
- Медленные загрузки с GitHub, где клонирование репозитория занимает полчаса?

Хватит мучиться! **Просто откройте браузер и начните кодить** — окружение настраивается автоматически, все зависимости предустановлены и готовы к работе.

> Теоретически любое устройство с браузером годится для VibeCoding — даже холодильник или смарт-часы.

## Предустановленное dev-окружение

Проект основан на образе, собранном и опубликованном [Eyre@VibeVibe.cn](https://www.hangkangfu.cn), и готов к работе из коробки:

- **AI Coding**: Claude Code, OpenAI Codex, Gemini Code Assist
- **Runtime**: Node.js 24.x, Python 3.11+, Docker
- **Инструменты разработки**: Git, GitHub CLI, VS Code (53 расширения)
- **Панель операций**: 1Panel (порт 34246, юзер `cnb`, пароль `IloveCNB.`)

Подробная конфигурация: [default-dev-env](https://cnb.cool/nfeyre/default-dev-env).

## Базовые концепции

| Концепция | Описание |
|-----|------|
| **Repository** | Место хранения кода, по сути папка проекта |
| **Organization** | Namespace для управления несколькими репозиториями и членами команды |
| **Fork** | Копия чужого репозитория в ваш аккаунт: можно свободно менять, не затрагивая оригинал |
| **Clone** | Скачивание удалённого репозитория локально для разработки |
| **Branch** | Независимая линия кода для параллельной разработки разных фич |

## 1. Регистрация и логин

Откройте Tencent Cloud [cnb.cool](https://cnb.cool) и отсканируйте WeChat-QR в правом верхнем углу для регистрации или входа.

![Scan to log in](/images/Advanced/image-20260203194524705.jpg)

![Registration page](/images/Advanced/image-20260203194703145.png)

### Верификация по реальному имени (обязательна)

После регистрации нужно пройти верификацию по реальному имени, прежде чем пользоваться сервисами CNB.

![Real-name verification](/images/Advanced/image-20260203194825714.png)

После верификации перейдите на [страницу верификации](https://cnb.cool/profile/auth):

![Verification page](/images/Advanced/image-20260203194851637.png)

![Fill in information](/images/Advanced/image-20260203194948051.png)

## 2. Создание организации

Репозитории CNB обязаны управляться внутри организации. Кликните `＋` в правом верхнем углу, выберите `Create Organization`, заполните имя организации и описание, затем кликните `Create`.

- [Страница создания организации](https://cnb.cool/new/groups)

![Create organization](/images/Advanced/image-20260203195108016.png)

![Enter organization name](/images/Advanced/image-20260203195234651.png)

Организация — это namespace для команд: управление членами и ресурсами. Прежде чем создавать ресурсы репозиториев, нужно создать организацию для управления членами, репозиториями и прочими ресурсами.

## 3. Создание dev-окружения

### Fork репозитория

Кликните, чтобы открыть репозиторий [vibestudio-default-dev](https://cnb.cool/vibevibe/vibestudio-default-dev), затем кликните Fork:

![Fork repository](/images/Advanced/image-20260203195620152.png)

### Запуск cloud-native разработки

После форка в собственный репозиторий кликните кнопку «Cloud-Native Development» и немного подождите создания dev-окружения:

![Start development environment](/images/Advanced/image-20260203195641644.png)

### Подключение к dev-окружению

После успешного создания workspace вы можете:

- Открыть WebIDE напрямую для онлайн-редактирования
- Использовать SSH-команду для подключения из IDE с установленным Remote SSH

![Connection methods](/images/Advanced/image-20260203200027101.png)

::: danger
**Важное напоминание:**

Любой код, изменённый в облачном IDE, **обязан быть закоммичен в Git и запушен!**

Cloud-native dev-окружение автоматически освобождается после простоя. Если код не запушен в удалённый репозиторий, он будет потерян при реклейме окружения.
:::

## 4. Настройка Claude Code

Окружение автоматически ставит зависимости, нужные для разработки. При открытии вас попросят настроить GLM KEY для использования Claude Code.

| Настройка Key | Разрешение буфера обмена |
|----------|-----------|
| ![Configure key](/images/Advanced/image-20260203200258701.png) | ![Clipboard permission](/images/Advanced/image-20260203200406122.png) |

При вставке ключа вас попросят доступ к буферу обмена компьютера — просто разрешите.

One-click настройка выделенного MCP для GLM-кодинг-пакета:

| Настройка MCP | Настройка завершена |
|----------|----------|
| ![Configure MCP](/images/Advanced/image-20260203200450374.png) | ![MCP configuration complete](/images/Advanced/image-20260203200500173.png) |

После настройки введите `claude` и начинайте coding-путешествие:

![Launch Claude](/images/Advanced/image-20260203200538588.png)

## 5. Подключение к репозиторию CNB локально

### Получение Access Token

После логина перейдите на страницу [Access Token](https://cnb.cool/profile/token) и создайте токен.

### Клонирование репозитория

```bash
git clone https://cnb.cool/your-org-name/repo-name.git
# Username: cnb
# Password: созданный вами access token
```

Подробнее: [официальная документация CNB — Access Token](https://docs.cnb.cool/zh/develops/token).

## Приложение

### 1. Переключение интерфейса на русский/китайский

Кликните кнопку Extensions в сайдбаре и установите языковой пакет (например, Chinese):

![Extensions button](/images/Advanced/image-20260203202605236.png)

Нажмите `Ctrl+Shift+P` для открытия «Command Palette», наберите `display` для фильтра и покажите команду «Configure Display Language», нажмите Enter:

![Command Palette](/images/Advanced/image-20260203202810201.png)

Выберите «Language» для переключения языка интерфейса:

![Select language](/images/Advanced/image-20260203202830872.png)

Выберите язык и подтвердите. После автоматического рестарта интерфейс переключится:

![Chinese interface](/images/Advanced/image-20260203202918342.png)

### 2. Миграция существующего локального проекта

Если у вас уже есть локальный проект, его можно мигрировать на CNB одним действием:

```bash
cnb-init-from https://your-repo-url.git
```

### 3. Что такое Access Token?

Access token — как ваш «цифровой ключ», используется для:

- Клонирования кода из удалённого репозитория
- Пуша кода в репозиторий
- Доступа к artifact-репозиторию

Как получить: после логина перейдите на страницу [Access Token](https://cnb.cool/profile/token) и создайте токен.

---

Больше информации — в [официальной документации CNB](https://docs.cnb.cool/zh/)
