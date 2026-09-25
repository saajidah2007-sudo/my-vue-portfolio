<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const roles = [
  "Aspiring Front-End Developer",
  "Web Development Learner",
  "Building & Learning",
];

const currentRole = ref(roles[0]);

let roleIndex = 0;
let roleInterval;

onMounted(() => {
  roleInterval = setInterval(() => {
    roleIndex = (roleIndex + 1) % roles.length;
    currentRole.value = roles[roleIndex];
  }, 3000);
});

onUnmounted(() => {
  clearInterval(roleInterval);
});

const scrollTo = (section) => {
  document.getElementById(section)?.scrollIntoView({
    behavior: "smooth",
  });
};
</script>

<template>
  <section class="hero" id="home">
    <div class="animated-bg"></div>

    <div class="hero-grid"></div>

    <div class="hero-content">
      <div class="hero-info">
        <p class="hero-small-title">HELLO, I'M</p>

        <h1>
          Saajidah
          <span>Abrahams</span>
        </h1>

        <div class="hero-role">
          <span class="role-line"></span>

          <Transition name="role" mode="out-in">
            <span :key="currentRole">
              {{ currentRole }}
            </span>
          </Transition>
        </div>

        <p class="hero-description">
          I enjoy building websites, trying out new ideas, and learning
          through real projects. I'm still growing as a developer, but
          every project gives me a chance to improve and learn something new.
        </p>

        <div class="hero-buttons">
          <button
            class="gold-button"
            @click="scrollTo('projects')"
          >
            View My Work
          </button>

          <button
            class="outline-button"
            @click="scrollTo('contact')"
          >
            Let's Connect
          </button>
        </div>
      </div>

      <div class="hero-image-wrapper">
        <div class="image-glow"></div>

        <div class="hero-image">
          <img
            src="https://i.ibb.co/4RR7RzGR/IMG-6617.png"
            alt="Saajidah Abrahams"
          />
        </div>
      </div>
    </div>

    <div class="scroll-indicator">
      <span>SCROLL TO EXPLORE</span>
      <div></div>
    </div>
  </section>
</template>