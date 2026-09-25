<script setup>
import { onMounted, onUnmounted, ref } from "vue";

import "./style.css";
import Navbar from "./components/Navbar.vue";
import Hero from "./components/Hero.vue";
import About from "./components/About.vue";
import Projects from "./components/Projects.vue";
import Skills from "./components/Skills.vue";
import Journey from "./components/Journey.vue";
import Contact from "./components/Contact.vue";
import Footer from "./components/Footer.vue";

const loading = ref(true);
const showBackToTop = ref(false);

const handleScroll = () => {
  showBackToTop.value = window.scrollY > 500;
};

const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: "smooth",
  });
};

onMounted(() => {
  setTimeout(() => {
    loading.value = false;
  }, 1800);

  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<template>
  <Transition name="loader">
    <div v-if="loading" class="loader-wrapper">
      <div class="loader-ring"></div>

      <div class="loader-content">
        <span class="loader-symbol">✦</span>

        <h1>WELCOME</h1>

        <p>Loading portfolio...</p>
      </div>
    </div>
  </Transition>

  <div class="portfolio">
    <Navbar />

    <main>
      <Hero />
      <About />
      <Projects />
      <Skills />
      <Journey />
      <Contact />
    </main>

    <Footer />

    <Transition name="fade">
      <button
        v-if="showBackToTop"
        class="back-to-top"
        @click="scrollToTop"
        aria-label="Back to top"
      >
        ↑
      </button>
    </Transition>
  </div>
</template>