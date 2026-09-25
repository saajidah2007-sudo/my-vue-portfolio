<template>
  <section id="contact" class="contact-section">
    <div class="section-heading">
      <span>CONTACT</span>
      <h2>Let's connect</h2>
    </div>

    <p class="contact-intro">
      Have a project in mind, want to connect, or just want to say hello?
      Feel free to reach out.
    </p>

    <div class="contact-wrapper">
      <form
        action="https://formspree.io/f/xjgdrpkr"
        method="POST"
        class="contact-form"
      >
        <div class="form-group">
          <label for="name">Name</label>

          <input
            id="name"
            type="text"
            name="name"
            placeholder="Your name"
            required
          />
        </div>

        <div class="form-group">
          <label for="email">Email</label>

          <input
            id="email"
            type="email"
            name="email"
            placeholder="your@email.com"
            required
          />
        </div>

        <div class="form-group">
          <label for="message">Message</label>

          <textarea
            id="message"
            name="message"
            rows="6"
            placeholder="Tell me what's on your mind..."
            required
          ></textarea>
        </div>

        <button type="submit" class="submit-btn">
          Send Message
        </button>
      </form>
    </div>

    <div class="contact-info-section">
      <h3>Find me online</h3>

      <div class="contact-links">
        <a
          href="mailto:saajidah2007@gmail.com"
          class="contact-link"
        >
          <span class="contact-icon">📧</span>

          <span class="contact-text">
            <strong>Email</strong>
            <p>saajidah2007@gmail.com</p>
          </span>
        </a>

        <a
          href="https://www.linkedin.com/in/saajidah-abrahams-440178414/"
          target="_blank"
          rel="noopener noreferrer"
          class="contact-link"
        >
          <span class="contact-icon">💼</span>

          <span class="contact-text">
            <strong>LinkedIn</strong>
            <p>View My Profile</p>
          </span>
        </a>

        <a
          href="https://github.com/saajidah2007-sudo"
          target="_blank"
          rel="noopener noreferrer"
          class="contact-link"
        >
          <span class="contact-icon">💻</span>

          <span class="contact-text">
            <strong>GitHub</strong>
            <p>View My Projects</p>
          </span>
        </a>

        <div class="contact-link location">
          <span class="contact-icon">📍</span>

          <span class="contact-text">
            <strong>Location</strong>
            <p>Cape Town, South Africa</p>
          </span>
        </div>
      </div>
    </div>
  </section>
</template>