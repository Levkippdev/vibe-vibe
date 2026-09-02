---
title: "1.0 Quick Start"
description: "Настройте окружение и начните AI-кодинг за 5 минут"
chapter: "Глава 1"
---

# 1.0 Quick Start

> **Прочитав этот раздел, вы сможете:**
>
> - Установить Git, Node.js и Claude Code
> - Настроить менеджер пакетов pnpm и китайское зеркало для ускорения загрузок
> - Настроить модель GLM и начать AI-кодинг

Этот раздел даёт простейший и самый прямой процесс настройки, чтобы вы могли быстро начать AI-кодинг.

> **Пользователь Windows?** Читайте дальше.
> **Пользователь Mac/Linux?** [Кликните, чтобы перейти к инструкции установки](#mac-linux-users)

---

## Пользователи Windows {#windows-users}

### 1. Установите [Git](https://git-scm.com/install/windows)

**Скачать**:<https://registry.npmmirror.com/-/binary/git-for-windows/v2.52.0.windows.1/Git-2.52.0-64-bit.exe>

![image-20260203180304836](/images/Advanced/image-20260203180304836.png)

После скачивания установите двойным кликом и **просто жмите «Далее»** (пропустите, если уже установлено).

### 2. Установите [Node.js](https://nodejs.org/zh-cn/download)![image-20260203180429883](/images/Advanced/image-20260203180429883.png)

**Скачать**:<https://npmmirror.com/mirrors/node/v24.13.0/node-v24.13.0-x64.msi>

После скачивания установите двойным кликом и **просто жмите «Далее»** (пропустите, если уже установлено).

### 3. Проверьте установку

Нажмите `Win + X`, выберите **Terminal (Admin)** или **Windows PowerShell** и выполните:

```powershell
git --version
node -v
```

Если отобразились номера версий — установка успешна.

![image-20260203180527608](/images/Advanced/image-20260203180527608.png)

Если видите сообщение «команда не распознана», закройте terminal и откройте снова. Если не помогло — перезагрузите компьютер.

### 4. Настройте китайское зеркало и установите pnpm

Выполните в PowerShell:

```powershell
npm config set registry https://registry.npmmirror.com/; npm install -g pnpm; pnpm setup; pnpm config set registry https://registry.npmmirror.com/
```

![image-20260203180609407](/images/Advanced/image-20260203180609407.png)

::: warning Ошибка политики выполнения PowerShell?

Если при выполнении команд в PowerShell вы получаете ошибку «cannot load script because running scripts is disabled on this system», запустите PowerShell от имени администратора и выполните:

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Затем повторите команду выше.

![image-20260203180635579](/images/Advanced/image-20260203180635579.png)

:::

### 5. Установите Claude Code

Выполните в PowerShell:

```powershell
npm install -g @anthropic-ai/claude-code
```

После окончания установки выполните:

```powershell
claude
```

Если вы видите приветственный экран Claude Code — установка успешна!

![image-20260203180714506](/images/Advanced/image-20260203180714506.png)

::: warning Если видите «No suitable shell found»

Это значит, что Git установлен некорректно. Задайте переменную окружения:

1. Нажмите `Win + S` и найдите «environment variables»

   ![image-20260203180856348](/images/Advanced/image-20260203180856348.png)

2. Кликните «Edit the system environment variables»

3. Кликните «Environment Variables»

   ![image-20260203180925214](/images/Advanced/image-20260203180925214.png)

4. В разделе «System variables» кликните «New»

5. Имя переменной: `CLAUDE_CODE_GIT_BASH_PATH`

6. Значение переменной: `C:\Program Files\Git\bin\bash.exe`

   ![image-20260203181030343](/images/Advanced/image-20260203181030343.png)

7. Нажмите OK для сохранения, затем **перезапустите PowerShell** и попробуйте снова

Если всё ещё не работает — удалите Git и установите заново.

:::

---

## Пользователи Mac/Linux {#mac-linux-users}

### 1. Установите Git

**macOS**:

- При первом вводе `git` в Terminal вам предложат установить Xcode Command Line Tools. Просто кликните Install.
- Или выполните вручную: `xcode-select --install`
- Если нужна свежая версия — используйте Homebrew: `brew install git`

**Linux**:

```bash
# Ubuntu/Debian
sudo apt update && sudo apt install git -y

# CentOS/RHEL
sudo yum install git -y
```

### 2. Откройте Terminal

- **Mac**: нажмите `Cmd + Space` и введите «Terminal»
- **Linux**: нажмите `Ctrl + Alt + T`

### 3. Запустите скрипт инициализации окружения

Этот скрипт автоматически установит Node.js, pnpm и настроит китайское зеркало:

**macOS:**

```bash
curl -fsSL https://cnb.cool/vibevibe/scripts/-/git/raw/main/init-node-mac.sh | sed 's/\r$//' | sh && npm install -g pnpm && pnpm config set registry https://registry.npmmirror.com/ && pnpm setup
```

**Linux:**

```bash
curl -fsSL https://cnb.cool/vibevibe/scripts/-/git/raw/main/init-node-linux.sh | sed 's/\r$//' | sh
```

После завершения скрипта **обязательно заново откройте окно terminal** (или выполните `source ~/.bashrc` / `source ~/.zshrc`), чтобы применить конфигурацию.

Скрипт автоматически настраивает: **nvm** (Node Version Manager — для переключения между версиями Node.js), **Node.js** (runtime для выполнения TypeScript-кода), **pnpm** (менеджер пакетов, более быстрый и экономный к месту, чем npm) и **китайское зеркало** (настраивает зеркало Taobao для ускорения загрузки зависимостей).

### 3. Проверьте установку

```bash
git --version
node -v
```

Если отобразились номера версий — установка успешна.

### 4. Установите Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

После окончания установки выполните:

```bash
claude
```

Если вы видите приветственный экран Claude Code — установка успешна!

---

## Настройка модели GLM {#config-glm}

Claude Code по умолчанию использует официальные модели Claude от Anthropic, но вы также можете настроить внутреннюю модель вроде GLM — она дешевле и быстрее в доступе.

**Шаг 1: Получите API Key**

Зайдите на [Zhipu Open Platform](https://open.bigmodel.cn/), кликните кнопку «Sign Up / Log In» в правом верхнем углу и следуйте подсказкам для регистрации. После входа перейдите в персональный центр, кликните [API Keys](https://bigmodel.cn/usercenter/proj-mgmt/apikeys) и создайте новый API Key.

![image-20260203181347764](/images/Advanced/image-20260203181347764.png)

![image-20260203181406471](/images/Advanced/image-20260203181406471.png)

**Шаг 2: Установка хелпера в один клик — автоматическая настройка**

Выполните в Terminal/PowerShell:

```bash
npx @z_ai/coding-helper
```

![Description](/images/Advanced/1764741445765coding-tool-helper.gifattname=coding-tool-helper.gif)

Введите полученный API Key — инструмент автоматически завершит все шаги настройки.

**Шаг 3: Проверьте настройку**

```bash
claude
```

Claude Code теперь будет использовать модель GLM для ответов на ваши вопросы.

::: tip Официальная документация

Подробнее о настройке: [GLM Official Documentation — Claude Code Configuration Guide](https://docs.bigmodel.cn/cn/coding-plan/tool/claude).

:::

::: tip Нужно управлять несколькими провайдерами моделей?

Если вам нужно часто переключаться между разными провайдерами AI-моделей (GLM, DeepSeek, OpenAI и др.), можно использовать [cc-switch](https://github.com/farion1231/cc-switch) — десктопный GUI-инструмент управления конфигурациями, поддерживающий Claude Code, Codex и Gemini CLI. Он позволяет переключать API-конфигурации одним кликом, централизованно управлять MCP-серверами и Skills, поддерживает спидтесты и быстрое переключение из системного трея.

![Main interface](/images/Advanced/main-zh.png)

:::

---

## Про nvm (опционально) {#about-nvm}

Скрипт инициализации для Mac/Linux автоматически устанавливает nvm (Node Version Manager). Если пользователи Windows хотят управлять несколькими версиями Node.js, установите nvm:

![image-20260203181915052](/images/Advanced/image-20260203181915052.png)

**Скачать**:<https://ghfast.top/https://github.com/coreybutler/nvm-windows/releases/download/1.2.2/nvm-setup.zip>

Или:<https://nvm.uihtm.com/nvm-1.2.2-setup.zip>

**После установки задайте зеркала**:

```powershell
nvm node_mirror https://npmmirror.com/mirrors/node/
nvm npm_mirror https://npmmirror.com/mirrors/npm/
```

**Частые команды**:

```bash
nvm install 24.13.0  # Установить конкретную версию
nvm use 24.13.0      # Использовать конкретную версию
nvm list             # Просмотреть установленные версии
```

::: details 🔄 Кликните, чтобы попробовать: менеджер версий Node
Попробуйте переключаться между разными версиями Node.js:

<NodeVersionManager />

> 💡 **Практика**: кликайте разные версии, чтобы переключаться, и наблюдайте, как меняется текущая.
>
> 🎯 **Ключевая идея**: nvm позволяет управлять несколькими версиями Node.js на одном компьютере.
:::

---

## FAQ {#faq}

### Q: Возникла ошибка при установке?

Скопируйте сообщение об ошибке и отдайте его AI-ассистенту. Он поможет решить.

### Q: Обязательно ли использовать GLM?

Нет. Claude Code по умолчанию использует официальные модели Claude от Anthropic, но для доступа из материкового Китая требуется relay-сервис. GLM — крайне выгодная альтернатива; также вы можете настроить другие внутренние модели: Minimax, Doubao, Qwen.



### Q: Я уже отдельно установил Node.js. Могу ли я теперь установить nvm?

Да. nvm управляет своими собственными версиями Node.js отдельно и не затронет ранее установленную. После установки nvm можно использовать `nvm use` для переключения версий или `nvm install` для установки новых.

---

## Следующие шаги {#next-steps}

Завершив настройку окружения, продолжайте читать:

- [1.1 Эволюция форматов кода](./01-code-formats.md)
- [1.2 Понимаем tech stack](./02-tech-stack.md)
- [1.5 Управление пакетами и конфигурация проекта](./05-package-manager-and-config.md)
- [1.7 Создайте свой первый проект](./07-creating-project.md)
