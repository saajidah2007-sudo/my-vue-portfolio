<script setup>
const journey = [
  {
    year: "2022",
    title: "Curiosity",
    icon: "🤔",
    text: "Developed an interest in technology and websites.",
  },
  {
    year: "2025",
    title: "Exploration",
    icon: "🧭",
    text: "Started learning more about web development.",
  },
  {
    year: "2025",
    title: "Growth",
    icon: "💡",
    text: "Started building projects using HTML, CSS and JavaScript.",
  },
  {
    year: "2026",
    title: "Vue",
    icon: "⚡",
    text: "Started learning Vue.js and building more structured applications.",
  },
];
</script>

<template>
  <section id="journey" class="journey-section">
    <div class="section-heading">
      <span>04 / JOURNEY</span>
      <h2>My learning journey</h2>
    </div>

    <div class="timeline">
      <div
        v-for="item in journey"
        :key="`${item.year}-${item.title}`"
        class="timeline-card"
      >
        <div class="timeline-year">
          {{ item.year }}
        </div>

        <div class="timeline-dot"></div>

        <div class="timeline-content">
          <h3>
            {{ item.title }}
            <span>{{ item.icon }}</span>
          </h3>

          <p>{{ item.text }}</p>
        </div>
      </div>
    </div>
  </section>
</template>