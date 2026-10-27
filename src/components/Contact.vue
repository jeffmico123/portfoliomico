<script setup>
import { profile } from '../data/content'

const channels = [
  { label: 'Email', value: profile.email, href: `mailto:${profile.email}` },
  { label: 'WhatsApp', value: profile.phone, href: profile.whatsapp },
  { label: 'GitHub', value: 'github.com/jeffmico123', href: profile.github },
  { label: 'LinkedIn', value: profile.name, href: profile.linkedin },
]
</script>

<template>
  <section id="contact" class="mx-auto max-w-6xl px-5 py-20">
    <div class="overflow-hidden rounded-3xl border border-white/8 bg-panel px-6 py-12 md:px-12">
      <p class="text-xs font-medium tracking-[0.28em] text-accent uppercase">Contact</p>
      <h2 class="font-display mt-3 max-w-xl text-3xl font-bold text-white md:text-4xl">
        Let’s build something reliable.
      </h2>
      <p class="mt-4 max-w-xl text-white/60">
        For project collaborations, web development, Shopify, or WordPress, email is the best way
        to reach me.
      </p>

      <div class="mt-8 flex flex-wrap gap-3">
        <a
          :href="`mailto:${profile.email}`"
          class="rounded-full bg-accent px-5 py-2.5 text-sm font-semibold text-ink transition hover:bg-white"
        >
          Email
        </a>
      </div>

      <dl class="mt-10 grid gap-4 sm:grid-cols-2">
        <div
          v-for="item in channels"
          :key="item.label"
          class="rounded-xl border border-white/8 bg-ink/50 p-4"
        >
          <dt class="text-xs tracking-wide text-white/40 uppercase">{{ item.label }}</dt>
          <dd class="mt-1">
            <a :href="item.href" target="_blank" rel="noreferrer" class="text-white hover:text-accent">
              {{ item.value }}
            </a>
          </dd>
        </div>
      </dl>
    </div>
  </section>
</template>
