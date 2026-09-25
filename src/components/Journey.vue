<script setup>
const journey = [
  {
    year: "2022",
    title: "Curiosity",
    icon: "🤔",
    text: "Developed an interest in technology and became curious about how websites and digital experiences are created.",
  },
  {
    year: "2025",
    title: "Discovering Life Choices",
    icon: "🧭",
    text: "Discovered Life Choices and found an opportunity to explore web development and start building a career in tech.",
  },
  {
    year: "2026",
    title: "Starting My Coding Journey",
    icon: "💻",
    text: "Started my internship journey at Life Choices and began learning the fundamentals of coding, including HTML, CSS, JavaScript, and Python.",
  },
  {
    year: "2026",
    title: "Building & Growing",
    icon: "💡",
    text: "Put my skills into practice by building projects and learning technologies such as Vue.js, Node.js, Express.js, and MySQL.",
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