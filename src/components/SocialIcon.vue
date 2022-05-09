<template>
  <div>
    <a
      v-for="(link, index) in links"
      :key="index"
      :href="link.url"
      target="_blank"
      ><i :class="link.class"></i
    ></a>
  </div>
</template>

<script>
export default {
  name: "SocialIcon",
  data() {
    return {
      links: [
        { url: "https://github.com/Shakil776", class: "bx bxl-github" },
        {
          url: "https://www.facebook.com/shakil776/",
          class: "bx bxl-facebook",
        },
        {
          url: "https://join.skype.com/invite/I5Uf7SYwjyuL",
          class: "bx bxl-skype",
        },
        {
          url: "https://www.linkedin.com/in/shakil776/",
          class: "bx bxl-linkedin",
        },
      ],
    };
  },
};
</script>

<style>
</style>