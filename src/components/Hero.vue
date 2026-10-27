<script setup>
import heroImg from '../assets/pics/jeffmico.png'
import { highlights, profile } from '../data/content'
</script>

<template>
  <section id="top" class="relative overflow-hidden pt-28 pb-20 md:pt-36 md:pb-28">
    <div class="pointer-events-none absolute inset-0 bg-grid opacity-60"></div>
    <div class="glow pointer-events-none absolute -top-24 right-0 h-96 w-96"></div>
    <div class="glow pointer-events-none absolute bottom-0 left-[-8rem] h-80 w-80 opacity-70"></div>

    <div class="relative mx-auto grid max-w-6xl items-center gap-12 px-5 md:grid-cols-[1.15fr_0.85fr]">
      <div>
        <p class="mb-4 text-xs font-medium tracking-[0.28em] text-accent uppercase">
          {{ profile.role }}
        </p>
        <h1 class="font-display text-5xl leading-[0.95] font-extrabold tracking-tight text-white sm:text-6xl lg:text-7xl">
          {{ profile.name }}
        </h1>
        <p class="mt-5 max-w-xl text-lg text-white/55">
          {{ profile.title }}
        </p>
        <p class="mt-5 max-w-xl text-base leading-relaxed text-white/75">
          {{ profile.tagline }}
        </p>

        <div class="mt-8 flex flex-wrap gap-3">
          <a
            href="#skills"
            class="rounded-full bg-accent px-5 py-2.5 text-sm font-semibold text-ink transition hover:bg-white"
          >
            View skills
          </a>
        </div>

        <dl class="mt-12 grid max-w-lg grid-cols-3 gap-4 border-t border-white/8 pt-8">
          <div v-for="item in highlights" :key="item.label">
            <dt class="font-display text-lg leading-tight font-bold text-white sm:text-xl">{{ item.value }}</dt>
            <dd class="mt-1 text-xs text-white/45">{{ item.label }}</dd>
          </div>
        </dl>
      </div>

      <div class="relative mx-auto w-full max-w-sm">
        <div class="absolute -inset-6 rounded-full bg-accent/15 blur-3xl"></div>
        <img
          :src="heroImg"
          :alt="profile.name"
          class="relative aspect-[4/5] w-full rounded-3xl object-cover object-[center_15%] ring-1 ring-white/10 drop-shadow-[0_20px_80px_rgba(46,230,214,0.18)]"
        />
      </div>
    </div>
  </section>
</template>
