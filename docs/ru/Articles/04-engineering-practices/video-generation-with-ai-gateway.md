---
title: Генерация видео через AI Gateway
description: Vercel AI Gateway поддерживает генерацию видео. С AI SDK 6 можно генерировать кинематографичное видео, синхронное аудио и персонализированный контент с консистентностью персонажей.
author: Jerilyn Zheng
source: https://vercel.com/blog/video-generation-with-ai-gateway
date: '2026-03-07'
category: 04-engineering-practices
tags:
  - Vercel
  - AI Gateway
  - Video Generation
  - AI SDK
---

# Генерация видео через AI Gateway

**Автор: Jerilyn Zheng**

**Оригинал: [Читать полную статью](https://vercel.com/blog/video-generation-with-ai-gateway)**

AI Gateway теперь поддерживает генерацию видео. Через AI SDK 6 вы можете генерировать видео кинематографического качества, синхронное аудио и персонализированный контент с консистентностью персонажей.

## Два способа начать

Генерация видео пока в стадии Beta — доступна на тарифах Pro и Enterprise и для платных пользователей AI Gateway.

### AI SDK 6: программная генерация видео

Вы можете генерировать видео программно — через тот же интерфейс, что и текст и картинки. Единый API, единый auth-флоу и единая observability-панель на всю цепочку AI-вызовов.

```typescript
import { experimental_generateVideo as generateVideo } from 'ai'

const { videos } = await generateVideo({
  model: 'xai/grok-imagine-video',
  prompt: 'A golden retriever catching a frisbee mid-air at the beach'
})
```

### AI Gateway Playground: no-code эксперименты

Также можно экспериментировать с видео-моделями прямо во встроенном [AI Gateway Playground](https://vercel.com/ai-gateway/models/grok-imagine-video) на странице модели — без предварительного кода. Можно сравнивать провайдеров, крутить промпты и скачивать результаты. Доступные модели — в [списке моделей](https://vercel.com/ai-gateway/models?capabilities=video-generation).

## Четыре стартовых видео-модели; 17 вариантов

- **Grok Imagine** (от xAI): быстрый, сильное следование инструкциям, подходит для быстрой генерации и редактирования видео со стайл-переносом.

- **Wan** (от Alibaba): силён в reference-based генерации и multi-shot нарративе, хорошо удерживает консистентность персонажей или субъектов.

- **Kling** (от Kuaishou): силён в image-to-video и нативной генерации аудио; новая модель 3.0 поддерживает multi-shot видео с автоматическими переходами между сценами.

- **Veo** (от Google): фокус на высокой визуальной фидельити и более сильной физической достоверности, плюс нативная генерация аудио — для кинематографичных кадров и сложных движений.

## Понимание видео-запросов

Видео-моделям нужно больше, чем «что вы хотите». В отличие от генерации картинок, видео-промпты обычно описывают и движение: перемещение камеры, действия субъекта, изменения во времени и опциональные аудио-указания. Провайдеры экспонируют специфичные способности через `providerOptions`, разблокируя разные режимы генерации. Конкретика — в [документации видеогенерации](https://vercel.com/docs/ai-gateway/capabilities/video-generation).

## Типы генерации

AI Gateway на старте поддерживает 4 типа видеогенерации:

| Тип | Вход | Описание | Примеры юзкейсов |
| --- | --- | --- | --- |
| Текст в видео | Текстовый промпт | Опишите сцену — получите видео | Реклама, объясняющие видео, соцконтент |
| Картинка в видео | Картинка, опционально текст | Добавить движение к статичной картинке | Продуктовые презентации, анимация логотипов, фотоэффекты |
| Первый-последний кадр | Две картинки, опционально текст | Задать начальное и конечное состояние — модель достраивает переход | До/после, таймлапсы, переходы |
| Референс в видео | Картинка или видео | Извлечь персонажа или субъекта из референса и поместить в новую сцену | Бренд-персонажи, серии видео с единым образом |

Текущие способности создателей моделей в AI Gateway:

| Создатель модели | Способности |
| --- | --- |
| xAI | Текст в видео, картинка в видео, редактирование видео, аудио |
| Wan | Текст в видео, картинка в видео, референс в видео, аудио |
| Kling | Текст в видео, картинка в видео, первый-последний кадр, аудио |
| Veo | Текст в видео, картинка в видео, аудио |

## Текст в видео

Опишите желаемое одними словами — и получите видео. Модель обрабатывает визуал, траектории движения и опциональное аудио — идеально для высококачественных шотов из лаконичных промптов.

### Пример: массовая программная генерация видео

Вы можете батчить видео для приложений, платформ или контент-пайплайнов по требованию — без традиционных съёмок и продакшна, только промпт и параметры.

Пример ниже использует `klingai/kling-v2.6-t2v`, генерируя видео заданного aspect ratio и длительности из текстового промпта.

```typescript
import { experimental_generateVideo as generateVideo } from 'ai'

const { videos } = await generateVideo({
  model: 'klingai/kling-v2.6-t2v',
  prompt: `Wide shot of a rocket lifting off from launch pad at dawn.
    Massive plume of orange fire and white smoke billows outward
    from the base. The rocket rises slowly at first, engines blazing,
    then accelerates upward. Pink and orange sunrise sky
    in the background. Ocean visible in the distance.`,
  aspectRatio: '16:9',
  duration: 5,
  providerOptions: {
    klingai: {
      mode: 'pro',
      sound: 'on'
    }
  }
})
```

### Пример: креативный контент

Короткие промпты можно превращать в более отточенные видео-клипы для соцсетей, рекламы или нарратива — с естественным движением и усиленной кинематографичностью.

Более конкретные, детальные промпты позволяют `google/veo-3.1-generate-001` генерировать видео с богатыми деталями и точным движением.

```typescript
import { experimental_generateVideo as generateVideo } from 'ai'

const { videos } = await generateVideo({
  model: 'google/veo-3.1-generate-001',
  prompt: `Close-up of a great horned owl turning its head slowly.
    Enormous yellow eyes with intricate iris detail.
    Every feather texture visible, from soft facial disc to ear tufts.
    The owl blinks once, deliberately.`,
  aspectRatio: '16:9'
})
```

## Картинка в видео

Подайте стартовую картинку и добавьте движение. Вы контролируете исходную композицию, а модель отвечает за динамику.

### Пример: анимация продуктовых картинок

Превращение существующих продуктовых изображений в более интерактивный видеоконтент.

`klingai/kling-v2.6-i2v` генерирует динамику для продуктового изображения по URL картинки и описанию движения в промпте.

```typescript
const { videos } = await generateVideo({
  model: 'klingai/kling-v2.6-i2v',
  prompt: {
    image: blackHoodie,
    text: `The orange tabby cat walks slowly across the black hoodie.
      Warm natural light. Cozy lifestyle scene. Smooth, cinematic.`
  },
  duration: 5,
  providerOptions: {
    klingai: { mode: 'pro' }
  }
})
```

### Пример: анимированные иллюстрации

Тонкое движение для статичных иллюстраций. Такой подход особенно подходит тематическому контенту или масштабному маркетинговому производству.

### Пример: lifestyle- и продуктовая фотография

Еда, напитки и lifestyle-картинки могут получить сдержанную естественную динамику — для производства соцконтента.

Здесь картинка кофе превращается в более интерактивное видео с тонкими изменениями света и деталей.

```typescript
import { experimental_generateVideo as generateVideo } from 'ai'

const { videos } = await generateVideo({
  model: 'alibaba/wan-v2.6-i2v',
  prompt: {
    image: 'https://your-storage.com/coffee-pour.png',
    text: `Coffee swirls gently in the cup, steam rises slowly,
     warm morning light shifts subtly`
  },
  resolution: '1280x720',
  duration: 3
})
```

## Первый-последний кадр

Вы задаёте начальное и конечное состояния — модель автоматически генерирует плавный переход между ними.

### Пример: сравнение «до/после»

Подходит для смены одежды, сравнения продуктов или временных изменений. Загрузите две картинки — получите естественно сшитый переход.

В примере ниже `klingai/kling-v3.0-i2v` использует `image` как стартовый кадр и `lastFrameImage` как финальный — модель достраивает трансформацию между ними.

```typescript
import { experimental_generateVideo as generateVideo } from 'ai'

const { videos } = await generateVideo({
  model: 'klingai/kling-v3.0-i2v',
  prompt: {
    image: startFrameDataUrl,
    text: `Smooth cinematic transition: The empty loft fills with furniture.
      A green velvet sofa fades into view, followed by a wooden coffee table.
      Potted plants rise from the floor. A patterned rug materializes.
      Framed artwork appears on the walls. Bookshelves on the back wall.
      Gentle, seamless transformation.`
  },
  duration: 5,
  providerOptions: {
    klingai: {
      lastFrameImage: endFrameDataUrl,
      mode: 'std'
    }
  }
})
```

## Референс в видео

Вы подаёте референсные картинки или видео людей/персонажей — модель извлекает черты внешности и генерирует новые сцены с ними в главной роли, по возможности сохраняя идентичность.

В примере ниже финальное видео генерируется по двум референсным картинкам собак.

С `alibaba/wan-v2.6-r2v-flash` вы соотносите несколько референсов через имена персонажей в промпте — `character1`, `character2` и т.д. Wan официально рекомендует эту запись для multi-reference генерации — результаты стабильнее.

```typescript
import { experimental_generateVideo as generateVideo } from 'ai'

const { videos } = await generateVideo({
  model: 'alibaba/wan-v2.6-r2v-flash',
  prompt: `character1 and character2 are playing together on the beach in San Francisco
    with the Golden Gate Bridge in the background, sunny day, waves crashing`,
  resolution: '1280x720',
  duration: 5,
  providerOptions: {
    alibaba: {
      referenceUrls: [shibaImage, yorkieImage]
    }
  }
})
```

## Редактирование видео

Можно менять и существующие видео — например, делать стайл-перенос. Подайте URL видео и опишите желаемые изменения — модель применит новый стиль, по возможности сохраняя исходное движение.

Здесь `xai/grok-imagine-video` превращает существующее видео в акварельный стиль.

```typescript
import { experimental_generateVideo as generateVideo } from 'ai'

const { videos } = await generateVideo({
  model: 'xai/grok-imagine-video',
  prompt: `Transform into watercolor painting style, soft flowing brushstrokes,
   paint bleeding at edges, delicate washes of color, artistic and dreamlike`,
  providerOptions: {
    xai: {
      videoUrl: dogVideo
    }
  }
})
```

## Начало работы

Больше примеров видео-моделей и детальных конфигов — в [документации видеогенерации](https://vercel.com/docs/ai-gateway/capabilities/video-generation).

Быстрый старт — в [quickstart по видеогенерации](https://vercel.com/docs/ai-gateway/getting-started/video).

В changelog моделей также постоянно добавляются новые примеры и техники промптинга.
