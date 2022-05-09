<template>
  <div class="container">
    <div class="section-title">
      <h2>Project</h2>
    </div>

    <div class="row" data-aos="fade-up">
      <div class="col-lg-12 d-flex justify-content-center">
        <ul id="portfolio-flters">
          <li data-filter="*" class="filter-active">{{ all }}</li>
          <li data-filter=".filter-html-css">{{ htmlCss }}</li>
          <li data-filter=".filter-laravel">{{ laravel }}</li>
          <li data-filter=".filter-vuejs">{{ vueJs }}</li>
          <li data-filter=".filter-php">{{ php }}</li>
        </ul>
      </div>
    </div>

    <div
      class="row portfolio-container"
      data-aos="fade-up"
      data-aos-delay="100"
    >
      <div
        v-for="(project, index) in projects"
        :key="index"
        class="col-lg-4 col-md-6 portfolio-item"
        :class="project.projectType"
      >
        <div class="portfolio-wrap">
          <img :src="project.image" class="img-fluid" alt="Project Image" />
          <div class="project-title">
            <h3>{{ project.projectTitle }}</h3>
          </div>
          <div class="portfolio-links">
            <a target="_blank" :href="project.link" title="Visit Project"
              ><i class="bx bx-link"></i
            ></a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Project",
  data() {
    return {
      projects: [
        {
          image: "assets/img/portfolio/consiii.png",
          link: "http://conseisiii.epizy.com",
          projectTitle: "ConsEISiii HTML",
          projectType: "filter-html-css",
        },
        {
          image: "assets/img/portfolio/ats.png",
          link: "http://ats.smartofficemate.co.uk/admin/admin-login",
          projectTitle: "ATS ADMIN. Email: admin@admin.com Pass: 123456",
          projectType: "filter-laravel",
        },
        {
          image: "assets/img/portfolio/ecom_dashboard.png",
          link: "http://dashboard-ecom.herokuapp.com/admin",
          projectTitle: "ECOM ADMIN PANEL",
          projectType: "filter-laravel",
        },
        {
          image: "assets/img/portfolio/onu.png",
          link: "http://onu-psd.epizy.com",
          projectTitle: "ONU PSD to HTML",
          projectType: "filter-html-css",
        },
        {
          image: "assets/img/portfolio/srms.png",
          link: "http://srm.epizy.com",
          projectTitle: "Result Management",
          projectType: "filter-php",
        },
        {
          image: "assets/img/portfolio/esellers.png",
          link: "http://esellers.epizy.com",
          projectTitle: "E-Sellers Ecom.",
          projectType: "filter-laravel",
        },
        {
          image: "assets/img/portfolio/sams.png",
          link: "http://sams.epizy.com",
          projectTitle: "Manage Attendance",
          projectType: "filter-php",
        },
        {
          image: "assets/img/portfolio/online_exam.png",
          link: "http://mcqtest.epizy.com",
          projectTitle: "Online MCQ Exam",
          projectType: "filter-php",
        },
        {
          image: "assets/img/portfolio/portfolio.png",
          link: "http://shakil.infinityfreeapp.com",
          projectTitle: "Portfolio",
          projectType: "filter-vuejs",
        },
        {
          image: "assets/img/portfolio/pickaboo.png",
          link: "http://pickaboo.epizy.com",
          projectTitle: "Clone Pickabo.com",
          projectType: "filter-html-css",
        },
        {
          image: "assets/img/portfolio/microsoft.png",
          link: "http://microsoft-clone.epizy.com",
          projectTitle: "Clone Microsoft.com",
          projectType: "filter-html-css",
        },
        {
          image: "assets/img/portfolio/tinyone.png",
          link: "http://tinyone-psd.epizy.com",
          projectTitle: "TinyOne PSD to HTML",
          projectType: "filter-html-css",
        },
        {
          image: "assets/img/portfolio/consi.png",
          link: "http://conseisi.epizy.com",
          projectTitle: "ConsEISi HTML",
          projectType: "filter-html-css",
        },
        {
          image: "assets/img/portfolio/consii.png",
          link: "http://conseisii.epizy.com",
          projectTitle: "ConsEISii HTML",
          projectType: "filter-html-css",
        },
      ],
      all: "All",
      htmlCss: "HTML | CSS | JS",
      vueJs: "Vue JS",
      laravel: "Laravel",
      php: "PHP OOP",
    };
  },
};
</script>

<style scoped>
.project-title {
  display: none;
}
.portfolio-wrap:hover .project-title {
  display: block;
  transition: all ease-in-out 0.3s;
  left: 0;
  right: 0;
  top: 0;
  z-index: 6;
  position: absolute;
  display: flex;
  justify-content: center;
}
</style>