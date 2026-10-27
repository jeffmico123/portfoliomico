<script setup>
import About from './components/About.vue'
import Contact from './components/Contact.vue'
import Education from './components/Education.vue'
import Experience from './components/Experience.vue'
import Footer from './components/Footer.vue'
import Hero from './components/Hero.vue'
import Navbar from './components/Navbar.vue'
import BasicInfo from './components/BasicInfo.vue'
import Skills from './components/Skills.vue'
</script>

<template>
  <Navbar />
  <main>
    <Hero />
    <About />
    <BasicInfo />
    <Skills />
    <Education />
    <Experience />
    <Contact />
  </main>
  <Footer />
</template>
