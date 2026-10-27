<script setup>
import { careerInterests, careerObjective, profile } from '../data/content'

const contactDetails = [
  { label: 'Location', value: profile.location },
  { label: 'Email', value: profile.email, href: `mailto:${profile.email}` },
  { label: 'Contact', value: profile.phone, href: `tel:${profile.phone}` },
]

const socialLinks = [
  { label: 'GitHub', href: profile.github },
  { label: 'LinkedIn', href: profile.linkedin },
]
</script>

<template>
  <section id="basics" class="mx-auto max-w-6xl px-5 py-20">
    <p class="text-xs font-medium tracking-[0.28em] text-accent uppercase">Profile</p>
    <h2 class="font-display mt-3 max-w-2xl text-3xl font-bold text-white md:text-4xl">
      Building skills for a future in web development.
    </h2>

    <div class="mt-8 grid gap-8 md:grid-cols-2">
      <div class="rounded-2xl border border-white/8 bg-panel p-6">
        <h3 class="font-display text-xl font-semibold text-white">Career objective</h3>
        <p class="mt-3 text-sm leading-relaxed text-white/60">{{ careerObjective }}</p>
        <h3 class="font-display mt-7 text-xl font-semibold text-white">Career interests</h3>
        <ul class="mt-4 flex flex-wrap gap-2">
          <li
            v-for="interest in careerInterests"
            :key="interest"
            class="rounded-full border border-white/10 px-3 py-1.5 text-xs text-white/65"
          >
            {{ interest }}
          </li>
        </ul>
      </div>

      <div class="rounded-2xl border border-white/8 bg-panel p-6">
        <h3 class="font-display text-xl font-semibold text-white">Basic information</h3>
        <dl class="mt-4 space-y-4">
          <div v-for="detail in contactDetails" :key="detail.label">
            <dt class="text-xs tracking-wide text-white/40 uppercase">{{ detail.label }}</dt>
            <dd class="mt-1 text-sm text-white/80">
              <a
                v-if="detail.href"
                :href="detail.href"
                class="transition hover:text-accent"
              >
                {{ detail.value }}
              </a>
              <span v-else>{{ detail.value }}</span>
            </dd>
          </div>
        </dl>
        <h3 class="font-display mt-7 text-xl font-semibold text-white">Professional profiles</h3>
        <ul class="mt-3 flex flex-wrap gap-4 text-sm">
          <li v-for="link in socialLinks" :key="link.label">
            <a :href="link.href" target="_blank" rel="noreferrer" class="text-accent hover:text-white">
              {{ link.label }}
            </a>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>
