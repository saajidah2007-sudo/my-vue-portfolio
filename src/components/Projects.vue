<script setup>
const featuredProjects = [
  {
    title: "HRFlow",
    description:
      "HRFlow was a group project developed for ModernTech Solutions. It is a Human Resources Management System designed to bring different HR processes into one place, including employee management, attendance, leave, payroll, performance, reports, and system settings. We built it using Vue.js, Node.js, Express.js, and MySQL, with each team member responsible for different sections before combining everything into the final system.",
    image: "https://i.ibb.co/0jFNyY1b/hr-flow.png",
    githubFrontend: "https://github.com/avivarendse/HRflow.git",
    githubBackend: "https://github.com/Zaarah-Okkers/ModernTech-Backend.git",
    live: "https://hrflow-xg3y.onrender.com/index.html",
    number: "01",
    login: {
      username: "admin@test.com",
      password: "Test1234!",
    },
  },

  {
    title: "RentoSphere",
    description:
      "RentoSphere was a group e-commerce project developed with Matthew, Lisekho and Purrity. It is an online rental marketplace that allows people to list items they own and gives others a convenient way to find and rent items they need for a short period of time. The platform includes rental listings, owner applications, listing management, earnings, safety verification, authentication and booking confirmations. We built the project using Vue.js, JavaScript, HTML, CSS, Node.js, Express.js and MySQL, while using Git and GitHub for collaboration.",
    image: "https://i.ibb.co/0jFNyY1b/hr-flow.png",
    github:
      "https://github.com/TaShepsta/E-Commerce-project.git",
    live:
      "https://e-commerce-project-ca0q.onrender.com",
    number: "02",
    bookingNote: "Renter account required for booking.",
  },
];

const miniProjects = [
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

    <!-- FEATURED PROJECTS -->
    <div class="section-heading">
      <span>02 / FEATURED PROJECTS</span>
      <h2>Projects I've worked on</h2>
    </div>

    <div class="projects-intro">
      <p>
        Larger projects I've worked on while developing my skills in
        front-end and full-stack web development.
      </p>
    </div>

    <div class="featured-projects">
      <article
        v-for="project in featuredProjects"
        :key="project.number"
        class="featured-project-card"
      >
        <div class="featured-project-image">

          <div v-if="project.image" class="project-image">
            <img
              :src="project.image"
              :alt="project.title"
            />
          </div>

          <div v-else class="project-image-placeholder">
            <span>PROJECT IMAGE</span>
          </div>

          <span class="project-number">
            {{ project.number }}
          </span>
        </div>

        <div class="featured-project-content">

          <div class="featured-project-label">
            FEATURED PROJECT
          </div>

          <h3>{{ project.title }}</h3>

          <p class="featured-description">
            {{ project.description }}
          </p>

          <!-- HRFLOW LOGIN -->
          <div
            v-if="project.login"
            class="demo-login"
          >
            <div class="demo-login-heading">
              <span>DEMO LOGIN</span>
            </div>

            <div class="login-details">
              <div>
                <small>Username</small>
                <strong>{{ project.login.username }}</strong>
              </div>

              <div>
                <small>Password</small>
                <strong>{{ project.login.password }}</strong>
              </div>
            </div>
          </div>

          <!-- RENTOSPHERE BOOKING NOTE -->
          <div
            v-if="project.bookingNote"
            class="booking-note"
          >
            <span>NOTE</span>
            <p>{{ project.bookingNote }}</p>
          </div>

          <div class="featured-project-buttons">

            <template v-if="project.githubFrontend">
              <a
                :href="project.githubFrontend"
                target="_blank"
                rel="noopener noreferrer"
                class="project-link"
              >
                Frontend GitHub
              </a>

              <a
                :href="project.githubBackend"
                target="_blank"
                rel="noopener noreferrer"
                class="project-link"
              >
                Backend GitHub
              </a>
            </template>

            <a
              v-else
              :href="project.github"
              target="_blank"
              rel="noopener noreferrer"
              class="project-link"
            >
              GitHub
            </a>

            <a
              :href="project.live"
              target="_blank"
              rel="noopener noreferrer"
              class="project-link filled"
            >
              Live Demo
            </a>

          </div>
        </div>
      </article>
    </div>


    <!-- MINI PROJECTS -->
    <div class="mini-projects-heading">
      <div class="section-heading">
        <span>03 / MINI PROJECTS</span>
        <h2>Smaller projects and exercises</h2>
      </div>

      <p>
        Smaller projects and exercises I completed while practising
        different front-end development concepts.
      </p>
    </div>

    <div class="cards mini-project-cards">
      <article
        v-for="project in miniProjects"
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
              GitHub
            </a>

            <a
              :href="project.live"
              target="_blank"
              rel="noopener noreferrer"
              class="project-link filled"
            >
              Live Demo
            </a>
          </div>

        </div>
      </article>
    </div>

  </section>
</template>