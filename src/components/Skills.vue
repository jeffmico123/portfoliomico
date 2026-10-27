<script setup>
import { skillGroups } from '../data/content'
</script>

<template>
  <section id="skills" class="mx-auto max-w-6xl px-5 py-20">
    <p class="text-xs font-medium tracking-[0.28em] text-accent uppercase">Skills</p>
    <h2 class="font-display mt-3 text-3xl font-bold text-white md:text-4xl">
      Technical & professional skills
    </h2>
    <p class="mt-4 max-w-2xl text-white/55">
      A growing toolkit built through coursework, hands-on projects, and professional experience.
    </p>

    <div class="mt-10 grid gap-4 sm:grid-cols-2 lg:grid-cols-3">
      <div
        v-for="group in skillGroups"
        :key="group.title"
        class="rounded-2xl border border-white/8 bg-panel p-5"
      >
        <h3 class="text-sm font-semibold tracking-wide text-accent">{{ group.title }}</h3>
        <ul class="mt-4 flex flex-wrap gap-2">
          <li
            v-for="item in group.items"
            :key="item.name"
            class="inline-flex items-center gap-2 rounded-lg bg-white/4 px-2.5 py-1.5 text-sm text-white/80"
          >
            <span
              v-if="item.logo"
              class="flex h-6 w-6 shrink-0 items-center justify-center rounded-md bg-white p-1"
            >
              <img :src="item.logo" :alt="item.name" width="16" height="16" class="h-4 w-4 object-contain" />
            </span>
            {{ item.name }}
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>
