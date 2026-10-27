<script setup>
import { education } from '../data/content'
</script>

<template>
  <section id="education" class="mx-auto max-w-6xl px-5 py-20">
    <p class="text-xs font-medium tracking-[0.28em] text-accent uppercase">Education</p>
    <h2 class="font-display mt-3 text-3xl font-bold text-white md:text-4xl">
      Academic background
    </h2>

    <ul class="mt-10 divide-y divide-white/8 rounded-2xl border border-white/8 bg-panel">
      <li
        v-for="item in education"
        :key="item.name"
        class="flex flex-col gap-1 px-5 py-4 sm:flex-row sm:items-center sm:justify-between"
      >
        <div>
          <p class="font-medium text-white">{{ item.name }}</p>
          <p class="text-sm text-white/45">{{ item.place }}</p>
        </div>
        <p v-if="item.year" class="text-sm text-accent">{{ item.year }}</p>
      </li>
    </ul>

  </section>
</template>
