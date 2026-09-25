<script setup>
import { ref } from "vue";

const skills = [
  {
    name: "HTML",
    level: 50,
  },
  {
    name: "CSS",
    level: 40,
  },
  {
    name: "JavaScript",
    level: 50,
  },
  {
    name: "Vue.js",
    level: 40,
  },
  {
    name: "Git & GitHub",
    level: 60,
  },
  {
    name: "Node.js",
    level: 35,
  },
];

const activeSkill = ref(null);
</script>

<template>
  <section id="skills" class="skills-section">
    <div class="section-heading skills-heading">
      <span class="skills-eyebrow">MY SKILLS</span>

      <h2>
        What I'm
        <span>Learning</span>
      </h2>

      <p>
        These are some of the technologies I've been working with while
        learning and building projects.
      </p>
    </div>

    <div class="skills-container">
      <article
        v-for="skill in skills"
        :key="skill.name"
        class="skill-card"
        :class="{ active: activeSkill === skill.name }"
        @mouseenter="activeSkill = skill.name"
        @mouseleave="activeSkill = null"
      >
        <div class="skill-card-top">
          <h3>{{ skill.name }}</h3>

          <span class="skill-percent">
            {{ skill.level }}%
          </span>
        </div>

        <div class="progress">
          <div
            class="progress-bar"
            :class="{ highlighted: activeSkill === skill.name }"
            :style="{ width: `${skill.level}%` }"
          ></div>
        </div>

        <p class="skill-status">
          Currently learning
        </p>
      </article>
    </div>

    <p class="skills-note">
      The percentages reflect my current confidence with each skill and where
      I am in my learning journey.
    </p>
  </section>
</template>