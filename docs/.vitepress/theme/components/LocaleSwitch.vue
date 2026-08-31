<script setup lang="ts">
import { computed } from 'vue'
import { useRoute } from 'vitepress'

defineProps<{
  screenMenu?: boolean
}>()

const route = useRoute()

const mirroredSectionPrefixes = ['/Basic/', '/Advanced/', '/Practice/', '/Articles/']

function isMirroredChinesePath(path: string) {
  return mirroredSectionPrefixes.some((prefix) => path.startsWith(prefix))
}

const isEnglish = computed(() => route.path.startsWith('/en/') || (route.path === '/' ? true : false))

const isRussian = computed(() => route.path.startsWith('/ru/'))

function stripLocale(path: string) {
  if (path.startsWith('/en/')) return path.slice(3)
  if (path.startsWith('/ru/')) return path.slice(4)
  return path
}

const englishHref = computed(() => {
  const path = route.path

  if (path === '/' || path === '/en/' || path === '/zh/' || path === '/ru/') return '/en/'

  if (path.startsWith('/en/')) return path

  const stripped = stripLocale(path)

  if (isMirroredChinesePath(stripped)) return `/en${stripped}`

  return '/en/'
})

const russianHref = computed(() => {
  const path = route.path

  if (path === '/' || path === '/en/' || path === '/zh/' || path === '/ru/') return '/ru/'

  const stripped = stripLocale(path)

  if (isMirroredChinesePath(stripped)) return `/ru${stripped}`

  return '/ru/'
})

const chineseHref = computed(() => {
  const path = route.path

  if (path === '/' || path === '/zh/' || path === '/en/' || path === '/ru/') return '/zh/'

  if (path.startsWith('/en/') || path.startsWith('/ru/')) {
    const stripped = stripLocale(path)
    return isMirroredChinesePath(stripped) ? stripped : '/zh/'
  }

  return path
})
</script>

<template>
  <div :class="['locale-switch', { 'locale-switch--mobile': screenMenu }]">
    <a
      class="locale-switch__link"
      :class="{ 'locale-switch__link--active': isEnglish }"
      :href="englishHref"
      :aria-current="isEnglish ? 'page' : undefined"
    >
      EN
    </a>
    <span class="locale-switch__divider">/</span>
    <a
      class="locale-switch__link"
      :class="{ 'locale-switch__link--active': isRussian }"
      :href="russianHref"
      :aria-current="isRussian ? 'page' : undefined"
    >
      RU
    </a>
    <span class="locale-switch__divider">/</span>
    <a
      class="locale-switch__link"
      :class="{ 'locale-switch__link--active': !isEnglish && !isRussian }"
      :href="chineseHref"
      :aria-current="!isEnglish && !isRussian ? 'page' : undefined"
    >
      中文
    </a>
  </div>
</template>

<style scoped>
.locale-switch {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-size: 13px;
  line-height: 1;
}

.locale-switch__link {
  color: var(--vp-c-text-2);
  text-decoration: none;
  font-weight: 600;
}

.locale-switch__link:hover,
.locale-switch__link--active {
  color: var(--vp-c-brand-1);
}

.locale-switch__divider {
  color: var(--vp-c-text-3);
}

.locale-switch--mobile {
  justify-content: center;
  width: 100%;
  margin-top: 8px;
}
</style>
