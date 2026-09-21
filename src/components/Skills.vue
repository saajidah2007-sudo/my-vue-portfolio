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
    <div class="section-heading">
      <span>03 / SKILLS</span>
      <h2>What I'm learning</h2>
    </div>

    <div class="skills-container">
      <div
        v-for="skill in skills"
        :key="skill.name"
        class="skill"
        @mouseenter="activeSkill = skill.name"
        @mouseleave="activeSkill = null"
      >
        <div class="skill-info">
          <span>{{ skill.name }}</span>

          <span class="skill-percent">
            {{ skill.level }}%
          </span>
        </div>

        <div class="progress">
          <div
            class="progress-bar"
            :class="{ highlighted: activeSkill === skill.name }"
            :style="{
              '--target-width': `${skill.level}%`
            }"
          ></div>
        </div>
      </div>
    </div>

    <p class="skills-note">
      These percentages represent my current confidence level while learning
      and practising.
    </p>
  </section>
</template>