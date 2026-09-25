<script setup>
const featuredProjects = [
  {
    title: "HRFlow",
    category: "Human Resources Management System",
    description:
      "HRFlow was a group project developed for ModernTech Solutions. It is a full-stack Human Resources Management System designed to bring employee management, attendance, leave, payroll, performance, reports, and system settings into one platform.",

    image: "https://i.ibb.co/0jFNyY1b/hr-flow.png",

    technologies: ["Vue.js", "Node.js", "Express.js", "MySQL"],

    frontendGithub: "https://github.com/avivarendse/HRflow.git",
    backendGithub: "https://github.com/Zaarah-Okkers/ModernTech-Backend.git",
    live: "https://hrflow-xg3y.onrender.com/index.html",

    number: "01",

    login: {
      username: "admin@test.com",
      password: "Test1234!",
    },
  },

  {
    title: "RentoSphere",
    category: "Rental Marketplace",
    description:
      "RentoSphere was a group e-commerce project developed with Matthew, Lisekho, and Purrity. The platform allows owners to list items for rent while renters can browse listings, request rentals, manage bookings, and receive booking confirmations.",

    image: "https://i.ibb.co/W4LrDP9x/Screenshot-2026-09-23-093017.png",

    technologies: ["Vue.js", "JavaScript", "Node.js", "Express.js", "MySQL"],

    github: "https://github.com/TaShepsta/E-Commerce-project.git",
    live: "https://e-commerce-project-ca0q.onrender.com",

    number: "02",

    bookingNote: "Renter account required for booking.",
  },
];

const miniProjects = [
  {
    title: "Responsive Image Gallery",
    description:
      "A responsive image gallery built while practising CSS layouts, spacing, responsive design, and image presentation.",

    technologies: ["HTML", "CSS"],

    image: "https://i.ibb.co/bjgDY0JY/Screenshot-2026-06-05-112231.png",

    github: "https://github.com/saajidah2007-sudo/CSS-Excercise-2.git",

    live: "https://image-gallery-css-project.netlify.app/",
  },

  {
    title: "Product Showcase Page",
    description:
      "A product-focused webpage created to practise page structure, styling, layout, and responsive design using HTML and CSS.",

    technologies: ["HTML", "CSS"],

    image: "https://i.ibb.co/rGVWdgcH/Screenshot-2026-06-05-115837.png",

    github: "https://github.com/saajidah2007-sudo/CSS-Exercise-3.git",

    live: "https://product-showcase-css-project.netlify.app/",
  },

  {
    title: "Bootstrap Store Website",
    description:
      "A small store website built while learning Bootstrap components, responsive layouts, navigation, cards, and page styling.",

    technologies: ["HTML", "CSS", "Bootstrap"],

    image: "https://i.ibb.co/nsJkDQhr/Screenshot-2026-06-05-120132.png",

    github: "https://github.com/saajidah2007-sudo/CSS-Exercise-4.git",

    live: "https://bootstrap-store-css-project.netlify.app/",
  },
];
</script>

<template>
  <section id="projects" class="projects-section">
    <div class="section-heading projects-heading">
      <span class="section-eyebrow">MY WORK</span>

      <h2>
        Projects I've
        <span>Built</span>
      </h2>

      <p>
        A selection of projects I've worked on while building my skills in
        front-end and full-stack development.
      </p>
    </div>

    <!-- =========================================
         FEATURED PROJECTS
    ========================================== -->

    <div class="featured-projects">
      <article
        v-for="(project, index) in featuredProjects"
        :key="project.title"
        class="featured-project-card"
        :class="{ 'featured-project-card-reverse': index % 2 !== 0 }"
      >
        <!-- PROJECT IMAGE -->
        <div class="featured-project-visual">
          <div class="project-number">
            {{ project.number }}
          </div>

          <div class="browser-window">
            <div class="browser-top">
              <div class="browser-dots">
                <span></span>
                <span></span>
                <span></span>
              </div>

              <div class="browser-address">
                <span>{{ project.title.toLowerCase() }}.app</span>
              </div>

              <div class="browser-space"></div>
            </div>

            <div class="browser-content">
              <img
                :src="project.image"
                :alt="`${project.title} project screenshot`"
                class="featured-project-screenshot"
              />
            </div>
          </div>
        </div>

        <!-- PROJECT INFORMATION -->
        <div class="featured-project-content">
          <div class="featured-label">
            <span></span>
            Featured Project
          </div>

          <div class="featured-project-title-row">
            <span class="featured-project-index">
              {{ project.number }}
            </span>

            <div>
              <p class="featured-project-category">
                {{ project.category }}
              </p>

              <h3>{{ project.title }}</h3>
            </div>
          </div>

          <p class="featured-project-description">
            {{ project.description }}
          </p>

          <!-- TECHNOLOGIES -->
          <div class="featured-technologies">
            <span v-for="technology in project.technologies" :key="technology">
              {{ technology }}
            </span>
          </div>

          <!-- HRFLOW LOGIN -->
          <div v-if="project.login" class="project-info-box login-box">
            <div class="info-box-heading">Demo Login</div>

            <div class="login-details">
              <div>
                <span>Username</span>
                <strong>{{ project.login.username }}</strong>
              </div>

              <div>
                <span>Password</span>
                <strong>{{ project.login.password }}</strong>
              </div>
            </div>
          </div>

          <!-- RENTOSPHERE BOOKING NOTE -->
          <div v-if="project.bookingNote" class="project-info-box booking-box">
            <span class="booking-dot"></span>

            <p>{{ project.bookingNote }}</p>
          </div>

          <!-- LINKS -->
          <div class="featured-project-links">
            <template v-if="project.frontendGithub">
              <a
                :href="project.frontendGithub"
                target="_blank"
                rel="noopener noreferrer"
                class="project-link project-link-primary"
              >
                Frontend GitHub
              </a>

              <a
                :href="project.backendGithub"
                target="_blank"
                rel="noopener noreferrer"
                class="project-link"
              >
                Backend GitHub
              </a>
            </template>

            <template v-else>
              <a
                :href="project.github"
                target="_blank"
                rel="noopener noreferrer"
                class="project-link project-link-primary"
              >
                GitHub
              </a>
            </template>

            <a
              :href="project.live"
              target="_blank"
              rel="noopener noreferrer"
              class="project-link project-link-live"
            >
              Live Demo
            </a>
          </div>
        </div>
      </article>
    </div>

    <!-- =========================================
         SMALLER PROJECTS
    ========================================== -->

    <div class="other-projects-heading">
      <div>
        <span class="section-eyebrow">MORE WORK</span>

        <h3>Smaller Projects</h3>
      </div>

      <p>
        Smaller projects that helped me practise the fundamentals and experiment
        with different layouts and technologies.
      </p>
    </div>

    <div class="projects-container">
      <article
        v-for="project in miniProjects"
        :key="project.title"
        class="project-card"
      >
        <!-- IMAGE -->
        <div class="project-card-image">
          <div class="mini-browser-bar">
            <span></span>
            <span></span>
            <span></span>
          </div>

          <div class="mini-project-screen">
            <img
              :src="project.image"
              :alt="`${project.title} project screenshot`"
            />
          </div>
        </div>

        <!-- CONTENT -->
        <div class="project-card-content">
          <h4>{{ project.title }}</h4>

          <p>
            {{ project.description }}
          </p>

          <div class="project-technologies">
            <span v-for="technology in project.technologies" :key="technology">
              {{ technology }}
            </span>
          </div>

          <div class="project-card-links">
            <a
              :href="project.github"
              target="_blank"
              rel="noopener noreferrer"
              class="mini-project-link"
            >
              GitHub
            </a>

            <a
              :href="project.live"
              target="_blank"
              rel="noopener noreferrer"
              class="mini-project-link mini-project-live"
            >
              Live Demo
            </a>
          </div>
        </div>
      </article>
    </div>
  </section>
</template>
