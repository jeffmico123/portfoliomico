<script setup>
import { schoolActivities } from '../data/content'
</script>

<template>
  <section id="experience" class="mx-auto max-w-6xl px-5 py-20">
    <p class="text-xs font-medium tracking-[0.28em] text-accent uppercase">Experience</p>
    <h2 class="font-display mt-3 text-3xl font-bold text-white md:text-4xl">
      School capstone & activities
    </h2>

    <div class="mt-8 grid gap-4 md:grid-cols-2">
      <article class="rounded-2xl border border-white/8 bg-panel p-6">
        <p class="text-xs font-medium tracking-wide text-accent uppercase">School capstone</p>
        <h3 class="font-display mt-2 text-xl font-semibold text-white">ProcureChain</h3>
        <p class="mt-3 text-sm text-white/60">Capstone project</p>
      </article>

      <article class="rounded-2xl border border-white/8 bg-panel p-6">
        <p class="text-xs font-medium tracking-wide text-accent uppercase">School activities</p>
        <ul class="mt-4 space-y-3">
          <li
            v-for="activity in schoolActivities"
            :key="activity"
            class="border-l-2 border-accent/50 pl-3 text-sm leading-relaxed text-white/75"
          >
            {{ activity }}
          </li>
        </ul>
      </article>
    </div>
  </section>
</template>
