<script setup>
const projects = [
  {
    title: "Responsive Image Gallery",
    description:
      "A responsive image gallery created to practise CSS layouts, image presentation and responsive design.",
    technologies: ["HTML", "CSS"],
    image:
      "https://i.ibb.co/bjgDY0JY/Screenshot-2026-06-05-112231.png",
    github:
      "https://github.com/saajidah2007-sudo/CSS-Excercise-2.git",
    live:
      "https://image-gallery-css-project.netlify.app/",
    number: "01",
  },

  {
    title: "Product Showcase Page",
    description:
      "A modern product display page created to improve my CSS styling, responsive layouts and visual presentation.",
    technologies: ["HTML", "CSS"],
    image:
      "https://i.ibb.co/rGVWdgcH/Screenshot-2026-06-05-115837.png",
    github:
      "https://github.com/saajidah2007-sudo/CSS-Exercise-3.git",
    live:
      "https://product-showcase-css-project.netlify.app/",
    number: "02",
  },

  {
    title: "Bootstrap Store Website",
    description:
      "An e-commerce style website built using Bootstrap, featuring responsive layouts, navigation components and modern design principles.",
    technologies: ["HTML", "CSS", "Bootstrap"],
    image:
      "https://i.ibb.co/nsJkDQhr/Screenshot-2026-06-05-120132.png",
    github:
      "https://github.com/saajidah2007-sudo/CSS-Exercise-4.git",
    live:
      "https://bootstrap-store-css-project.netlify.app/",
    number: "03",
  },
];
</script>

<template>
  <section id="projects" class="projects-section">
    <div class="section-heading">
      <span>02 / PROJECTS</span>
      <h2>Things I've built</h2>
    </div>

    <div class="projects-intro">
      <p>
        A few projects I've worked on while learning and experimenting with
        front-end development.
      </p>
    </div>

    <div class="cards">
      <article
        v-for="project in projects"
        :key="project.number"
        class="project-card"
      >
        <div class="project-image">
          <img
            :src="project.image"
            :alt="project.title"
          />

          <span class="project-number">
            {{ project.number }}
          </span>
        </div>

        <div class="project-content">
          <h3>{{ project.title }}</h3>

          <p>
            {{ project.description }}
          </p>

          <div class="technologies">
            <span
              v-for="technology in project.technologies"
              :key="technology"
            >
              {{ technology }}
            </span>
          </div>

          <div class="project-btns">
            <a
              :href="project.github"
              target="_blank"
              rel="noopener noreferrer"
              class="project-link"
            >
              GitHub ↗
            </a>

            <a
              :href="project.live"
              target="_blank"
              rel="noopener noreferrer"
              class="project-link filled"
            >
              Live Demo ↗
            </a>
          </div>
        </div>
      </article>
    </div>
  </section>
</template>