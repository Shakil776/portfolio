<template>
  <div class="container">
    <div class="section-title">
      <h2>Skills</h2>
    </div>

    <div class="row skills-content">
      <div
        class="col-lg-6"
        data-aos="fade-up"
        v-for="(group, i) in skillsGroups"
        :key="i"
      >
        <div
          class="progress"
          v-for="(skill, index) in skills.slice(
            i * itemsPerRow,
            (i + 1) * itemsPerRow
          )"
          :key="index"
        >
          <span class="skill"
            >{{ skill.lang }} <i class="val">{{ skill.percent }}%</i></span
          >
          <div
            class="progress-bar-wrap"
            :style="{
              background: skill.color,
              width: skill.percent + '%',
            }"
          ></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Skills",
  data() {
    return {
      itemsPerRow: 3,
      skills: [
        { lang: "HTML5", percent: 90, color: "#ec407a" },
        { lang: "CSS3", percent: 80, color: "#f4511e" },
        { lang: "JAVASCRIPT", percent: 80, color: "#512da8" },
        { lang: "VUE JS", percent: 75, color: "#f57c00" },
        { lang: "PHP", percent: 80, color: "#0288d1" },
        { lang: "Laravel", percent: 70, color: "#f4511e" },
      ],
    };
  },
  computed: {
    skillsGroups() {
      return Array.from(
        Array(Math.ceil(this.skills.length / this.itemsPerRow)).keys()
      );
    },
  },
  methods: {},
};
</script>

<style>
</style>