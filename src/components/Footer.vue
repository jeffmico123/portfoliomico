<script setup>
import { profile } from '../data/content'

const year = new Date().getFullYear()
</script>

<template>
  <footer class="border-t border-white/8">
    <div
      class="mx-auto flex max-w-6xl flex-col items-start justify-between gap-4 px-5 py-8 text-sm text-white/40 sm:flex-row sm:items-center"
    >
      <p>© {{ year }} {{ profile.name }}</p>
      <div class="flex gap-5">
        <a :href="profile.github" target="_blank" rel="noreferrer" class="hover:text-accent">GitHub</a>
        <a :href="profile.linkedin" target="_blank" rel="noreferrer" class="hover:text-accent">LinkedIn</a>
        <a :href="`mailto:${profile.email}`" class="hover:text-accent">Email</a>
      </div>
    </div>
  </footer>
</template>
