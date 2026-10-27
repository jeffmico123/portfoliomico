<script setup>
import { onMounted, onUnmounted, ref } from 'vue'
import { navLinks } from '../data/content'

const open = ref(false)
const scrolled = ref(false)
const active = ref('')

function onScroll() {
  scrolled.value = window.scrollY > 12
}

function close() {
  open.value = false
}

onMounted(() => {
  onScroll()
  window.addEventListener('scroll', onScroll, { passive: true })

  const ids = navLinks.map((link) => link.href.slice(1))
  const observer = new IntersectionObserver(
    (entries) => {
      const visible = entries
        .filter((entry) => entry.isIntersecting)
        .sort((a, b) => b.intersectionRatio - a.intersectionRatio)[0]
      if (visible) active.value = visible.target.id
    },
    { rootMargin: '-35% 0px -50% 0px', threshold: [0.1, 0.25, 0.5] },
  )

  ids.forEach((id) => {
    const el = document.getElementById(id)
    if (el) observer.observe(el)
  })

  onUnmounted(() => observer.disconnect())
})

onUnmounted(() => {
  window.removeEventListener('scroll', onScroll)
})
</script>

<template>
  <header
    class="fixed inset-x-0 top-0 z-50 transition-colors"
    :class="scrolled || open ? 'border-b border-white/8 bg-ink/80 backdrop-blur-xl' : ''"
  >
    <nav class="mx-auto flex max-w-6xl items-center justify-between px-5 py-4">
      <a href="#top" class="font-display text-lg font-bold tracking-tight text-white">
        JG<span class="text-accent">.</span>
      </a>

      <ul class="hidden items-center gap-7 text-sm text-white/60 md:flex">
        <li v-for="link in navLinks" :key="link.href">
          <a
            :href="link.href"
            class="transition-colors hover:text-white"
            :class="active === link.href.slice(1) ? 'text-accent' : ''"
          >
            {{ link.label }}
          </a>
        </li>
      </ul>

      <button
        type="button"
        class="inline-flex h-10 w-10 items-center justify-center rounded-lg border border-white/10 text-white md:hidden"
        :aria-expanded="open"
        aria-label="Toggle menu"
        @click="open = !open"
      >
        <span class="sr-only">Menu</span>
        {{ open ? '✕' : '☰' }}
      </button>
    </nav>

    <div v-if="open" class="border-t border-white/8 bg-ink/95 px-5 py-4 md:hidden">
      <ul class="flex flex-col gap-3 text-sm">
        <li v-for="link in navLinks" :key="link.href">
          <a :href="link.href" class="block py-1 text-white/80" @click="close">
            {{ link.label }}
          </a>
        </li>
      </ul>
    </div>
  </header>
</template>
