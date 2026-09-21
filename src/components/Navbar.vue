<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const menuOpen = ref(false);
const activeSection = ref("home");

const sections = [
  { id: "home", label: "Home" },
  { id: "about", label: "About" },
  { id: "projects", label: "Projects" },
  { id: "skills", label: "Skills" },
  { id: "journey", label: "Journey" },
  { id: "contact", label: "Contact" },
];

const scrollToSection = (id) => {
  menuOpen.value = false;

  document.getElementById(id)?.scrollIntoView({
    behavior: "smooth",
  });
};

const updateActiveSection = () => {
  const scrollPosition = window.scrollY + 200;

  for (const section of sections) {
    const element = document.getElementById(section.id);

    if (
      element &&
      scrollPosition >= element.offsetTop &&
      scrollPosition < element.offsetTop + element.offsetHeight
    ) {
      activeSection.value = section.id;
      break;
    }
  }
};

onMounted(() => {
  window.addEventListener("scroll", updateActiveSection);
  updateActiveSection();
});

onUnmounted(() => {
  window.removeEventListener("scroll", updateActiveSection);
});
</script>

<template>
  <header class="site-header">
    <nav class="navbar">
      <button
        class="logo"
        @click="scrollToSection('home')"
        aria-label="Go to home"
      >
        SA
      </button>

      <button
        class="mobile-toggle"
        :class="{ open: menuOpen }"
        @click="menuOpen = !menuOpen"
        aria-label="Toggle navigation"
        :aria-expanded="menuOpen"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>

      <ul class="nav-links" :class="{ open: menuOpen }">
        <li v-for="section in sections" :key="section.id">
          <button
            :class="{ active: activeSection === section.id }"
            @click="scrollToSection(section.id)"
          >
            {{ section.label }}
          </button>
        </li>
      </ul>
    </nav>
  </header>
</template>