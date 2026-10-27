<script setup>
import { profile } from '../data/content'
</script>

<template>
  <section id="about" class="mx-auto max-w-6xl px-5 py-20">
    <div class="grid gap-10 md:grid-cols-[0.4fr_0.6fr] md:gap-16">
      <div>
        <p class="text-xs font-medium tracking-[0.28em] text-accent uppercase">About</p>
        <h2 class="font-display mt-3 text-3xl font-bold text-white md:text-4xl">
          A student developer focused on building useful things for the web.
        </h2>
      </div>
      <div class="space-y-5 text-base leading-relaxed text-white/70">
        <p>{{ profile.summary }}</p>
        <p>
          Based in {{ profile.location }}, I value curiosity, steady improvement, and working well
          with others to solve practical problems.
        </p>
      </div>
    </div>
  </section>
</template>
