---
title: "5.2 Библиотеки компонентов"
description: "shadcn/ui, Ant Design, Element Plus, TDesign...когда использовать какие готовые блоки?"
---

# 5.2 Библиотеки компонентов

> **Цель раздела**: понять характеристики и лучшие сценарии использования мейнстримных библиотек компонентов и научиться выбирать правильную под потребности проекта.

Библиотека компонентов — как набор готовых «Lego-блоков». Не нужно каждый раз руками кодить кнопки, поля ввода или диалоги — берите уже построенное. Как говорят ветераны: «Выбери правильную библиотеку компонентов — и сэкономишь 80% UI-работы».

## shadcn/ui (рекомендуется)

[shadcn/ui](https://ui.shadcn.com/)

![image-20260222210620318](/images/Advanced/image-20260222210620318.png)

Она уже была представлена в предисловии, но здесь копнём глубже — почему это топ-выбор для VibeCoding.

**Ключевая идея**: это не npm-пакет. Исходный код компонентов копируется прямо в ваш проект. У вас полный контроль.

![image-20260222210651904](/images/Advanced/image-20260222210651904.png)

**Почему она отлично подходит для AI-разработки**:

С традиционными библиотеками код погребён глубоко в `node_modules` — AI не может его видеть или менять; с shadcn/ui код живёт прямо в папке вашего проекта, и AI может редактировать его как код, написанный вами самими.

- Код живёт в вашем проекте, поэтому AI может читать и менять его напрямую
- Высококачественные компоненты с солидной поддержкой доступности — например, юзеры с нарушениями зрения на screen reader'ах всё равно могут нормально взаимодействовать с кнопками и формами
- Богатая экосистема с множеством расширений-компонентов и шаблонов

**Как помочь AI хорошо использовать shadcn/ui**:

Скажите AI, что ваш проект использует shadcn/ui, — и он будет приоритизировать эти компоненты.

![image-20260222210713180](/images/Advanced/image-20260222210713180.png)

**Расширения экосистемы shadcn/ui**:

Экосистема shadcn/ui продолжает расти, и сообщество внесло много качественных расширений:

| Библиотека-расширение | Сценарий |
|-------|------|
| [Magic UI](https://magicui.design/) | Анимационные компоненты, компоненты спецэффектов |
| [Aceternity](https://www.aceternity.com/) | Компоненты продвинутых UI-эффектов |

<table><tbody>
  <tr>
    <td><img src="/images/Advanced/image-20260222210923284.png" /></td>
    <td><img src="/images/Advanced/image-20260222210905692.png" /></td>
  </tr>
</tbody></table>

## Другие мейнстримные библиотеки компонентов

<div class="lib-grid">

<a href="https://ant.design/" target="_blank" class="lib-card">
  <img src="/images/Advanced/image-20260222211429267.png" />
  <div class="lib-card-header">
    <span class="lib-card-name">Ant Design</span>
    <span class="lib-card-badge lib-badge-react">React</span>
  </div>
  <div class="lib-card-desc">Enterprise-библиотека компонентов от Alibaba: 60+ компонентов, покрывающих почти каждый сценарий, и самая обстоятельная китайская документация.</div>
  <div class="lib-card-tags">
    <span class="lib-card-tag">Админ-панели</span>
    <span class="lib-card-tag">Enterprise-инструменты</span>
    <span class="lib-card-tag">Data-intensive</span>
  </div>
</a>

<a href="https://element-plus.org/zh-CN/" target="_blank" class="lib-card">
  <img src="/images/Advanced/image-20260222212101447.png" />

  <div class="lib-card-header">
    <span class="lib-card-name">Element Plus</span>
    <span class="lib-card-badge lib-badge-vue">Vue 3</span>
  </div>
  <div class="lib-card-desc">Построена командой Ele.me — самая мейнстримная библиотека компонентов в экосистеме Vue 3. Если вы строите админ-backend на Vue — это в основном дефолтный выбор.</div>
  <div class="lib-card-tags">
    <span class="lib-card-tag">Топ-выбор для Vue</span>
    <span class="lib-card-tag">Админ-панели</span>
    <span class="lib-card-tag">Китайские доки</span>
  </div>
</a>

<a href="https://tdesign.tencent.com/" target="_blank" class="lib-card">
  <img src="/images/Advanced/image-20260222212117578.png" />
  <div class="lib-card-header">
    <span class="lib-card-name">TDesign</span>
    <span class="lib-card-badge lib-badge-multi">Multi-framework</span>
  </div>
  <div class="lib-card-desc">От Tencent: поддержка React, Vue 2/3 и мини-программ. Даёт полную дизайн-систему и предоставляет Figma-ресурсы.</div>
  <div class="lib-card-tags">
    <span class="lib-card-tag">React/Vue/мини-программы</span>
    <span class="lib-card-tag">Дизайн-система</span>
  </div>
</a>

<a href="https://arco.design/" target="_blank" class="lib-card">
  <img src="/images/Advanced/image-20260222212134560.png" />
  <div class="lib-card-header">
    <span class="lib-card-name">Arco Design</span>
    <span class="lib-card-badge lib-badge-multi">React / Vue</span>
  </div>
  <div class="lib-card-desc">От ByteDance: 60+ компонентов, проверенных на масштабе, плюс встроенная библиотека иконок и платформа конфигурации стилей.</div>
  <div class="lib-card-tags">
    <span class="lib-card-tag">Data-intensive</span>
    <span class="lib-card-tag">Кастомизация темы</span>
  </div>
</a>

<a href="https://m3.material.io/" target="_blank" class="lib-card">
  <img src="/images/Advanced/image-20260222222521284.png" />
  <div class="lib-card-header">
    <span class="lib-card-name">Material Design 3</span>
    <span class="lib-card-badge lib-badge-multi">Official Google</span>
  </div>
  <div class="lib-card-desc">Официальная дизайн-система Google (сейчас обновлена до версии 3), определяющая стандарты цветов, типографики, компонентов и др. Это не библиотека компонентов, а сам язык дизайна.</div>
  <div class="lib-card-tags">
    <span class="lib-card-tag">Дизайн-система</span>
    <span class="lib-card-tag">Кроссплатформенность</span>
    <span class="lib-card-tag">Dynamic Color</span>
  </div>
</a>

<a href="https://mui.com/" target="_blank" class="lib-card">
  <img src="/images/Advanced/image-20260222211543203.png" />
  <div class="lib-card-header">
    <span class="lib-card-name">MUI (Material UI)</span>
    <span class="lib-card-badge lib-badge-react">React</span>
  </div>
  <div class="lib-card-desc">Сторонняя React-библиотека компонентов на базе спецификации Material Design от Google. Самая широко используемая в мире, с сильными возможностями кастомизации темы.</div>
  <div class="lib-card-tags">
    <span class="lib-card-tag">Material Design</span>
    <span class="lib-card-tag">Интернационализация</span>
  </div>
</a>

<a href="https://www.radix-ui.com/" target="_blank" class="lib-card">
  <img src="/images/Advanced/image-20260222211603616.png" />
  <div class="lib-card-header">
    <span class="lib-card-name">Radix UI</span>
    <span class="lib-card-badge lib-badge-react">React</span>
  </div>
  <div class="lib-card-desc">Нестайленная low-level библиотека компонентов: обрабатывает только поведение и доступность — стилизация полностью на вас. Это фундамент shadcn/ui.</div>
  <div class="lib-card-tags">
    <span class="lib-card-tag">Unstyled</span>
    <span class="lib-card-tag">Доступность</span>
    <span class="lib-card-tag">Полная кастомизация</span>
  </div>
</a>

<a href="https://www.heroui.com/" target="_blank" class="lib-card">
  <img src="/images/Advanced/image-20260222212148692.png" />
  <div class="lib-card-header">
    <span class="lib-card-name">HeroUI</span>
    <span class="lib-card-badge lib-badge-react">React</span>
  </div>
  <div class="lib-card-desc">Ранее NextUI: построена на Tailwind CSS, отлично выглядит из коробки, со встроенными анимациями.</div>
  <div class="lib-card-tags">
    <span class="lib-card-tag">Tailwind CSS</span>
    <span class="lib-card-tag">Из коробки</span>
    <span class="lib-card-tag">Современный вид</span>
  </div>
</a>

</div>



## Дерево решений выбора библиотеки компонентов

<LibraryDecisionTree />

## Пусть AI поможет использовать библиотеки компонентов

Какую бы библиотеку вы ни выбрали, ключ — **ясно сказать AI, какую именно вы используете**, в промпте:

> «Используй компонент Table из shadcn/ui, чтобы показать список юзеров с сортировкой и пагинацией»

> «Используй Ant Design, чтобы построить таблицу управления заказами с фильтрацией и экспортом»

---

::: info Следующий шаг

Библиотеки компонентов решают проблему статичных интерфейсов. Хотите, чтобы страницы «ожили»? Продолжайте: [5.3 Библиотеки анимаций и интеракций](./03-animation-libraries.md).
:::
