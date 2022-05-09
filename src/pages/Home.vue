<template>
  <div>
    <header id="header">
      <div class="d-flex flex-column">
        <div class="profile">
          <img
            src="assets/img/profile.jpg"
            alt="Profile Photo"
            class="img-fluid rounded-circle"
          />
          <h1 class="text-light">
            <p class="nameS">{{ name }}</p>
            <p class="mobileNo">{{ mobile }}</p>
            <p class="emailAdd">{{ email }}</p>
          </h1>
          <div class="social-links mt-3 text-center">
            <social-icon></social-icon>
          </div>
        </div>

        <scrollactive
          active-class="active"
          :offset="0"
          :duration="300"
          id="navbar"
          class="nav-menu navbar"
        >
          <ul>
            <li v-for="(item, index) in navsItms" :key="index">
              <a :href="item.id" class="nav-link scrollactive-item"
                ><i :class="item.iconClass"></i> <span>{{ item.name }}</span></a
              >
            </li>
          </ul>
        </scrollactive>
      </div>
    </header>

    <section id="home" class="d-flex justify-content-center position-relative">
      <div class="hero-container" data-aos="fade-in">
        <h1 class="home">{{ name }}</h1>
        <p class="home">{{ designation }}</p>
      </div>

      <div class="download-cv">
        <a
          href="https://drive.google.com/file/d/1aqGlgbfHBchLs0PsmccBa--glz2xveAT/view"
          class="btn btn-success"
          target="_blank"
          >Download CV</a
        >
      </div>
    </section>

    <main id="main">
      <section id="about" class="about">
        <about></about>
      </section>

      <section id="skills" class="skills section-bg">
        <skills></skills>
      </section>

      <section id="resume" class="resume">
        <resume></resume>
      </section>

      <section id="project" class="portfolio section-bg">
        <project></project>
      </section>

      <section id="contact" class="contact">
        <contact></contact>
      </section>
    </main>
  </div>
</template>

<script>
import SocialIcon from "../components/SocialIcon.vue";
import About from "../components/About.vue";
import Skills from "../components/Skills.vue";
import Resume from "../components/Resume.vue";
import Project from "../components/Project.vue";
import Contact from "../components/Contact.vue";
export default {
  name: "Home",
  components: { SocialIcon, About, Skills, Resume, Project, Contact },
  data() {
    return {
      designation: "Web Developer",
      name: "Shakil Hossain",
      mobile: "+880 1738620241",
      email: "mdshakilhossain091@gmail.com",
      navsItms: [
        { name: "Home", iconClass: "bx bx-home", id: "#home" },
        { name: "About", iconClass: "bx bx-user", id: "#about" },
        { name: "Skills", iconClass: "bx bx-server", id: "#skills" },
        { name: "Resume", iconClass: "bx bx-file-blank", id: "#resume" },
        { name: "Project", iconClass: "bx bx-book-content", id: "#project" },
        { name: "Contact", iconClass: "bx bx-envelope", id: "#contact" },
      ],
    };
  },

  methods: {},
};
</script>

<style scoped>
.mobileNo {
  font-size: 14px;
  margin-bottom: 3px;
}
.emailAdd {
  font-size: 14px;
}
.nameS {
  margin-bottom: 5px;
}
.home {
  color: #149ddd !important;
  text-transform: uppercase;
}
.download-cv {
  position: absolute;
  top: 10%;
  right: 1%;
  z-index: 1;
}
</style>