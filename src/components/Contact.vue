<template>
  <div class="container">
    <div class="section-title">
      <h2>Contact</h2>
    </div>

    <div class="row" data-aos="fade-in">
      <div class="col-lg-5 d-flex align-items-stretch">
        <div class="info">
          <div class="address">
            <i class="bi bi-geo-alt"></i>
            <h4>Location</h4>
            <p>State guest house, Padma, Meghna, Dhaka</p>
          </div>

          <div class="email">
            <i class="bi bi-envelope"></i>
            <h4>Email</h4>
            <p>mdshakilhossain091@gmail.com</p>
          </div>

          <div class="phone">
            <i class="bi bi-phone"></i>
            <h4>Mobile</h4>
            <p>+880 1738620241</p>
          </div>
        </div>
      </div>

      <div class="col-lg-7 mt-5 mt-lg-0 d-flex align-items-stretch">
        <form @submit.prevent="sendEmail" role="form" class="php-email-form">
          <div class="row">
            <div class="form-group col-md-6">
              <label for="name"
                >Name&nbsp;<sup class="text-danger">*</sup></label
              >
              <input
                type="text"
                name="name"
                class="form-control"
                id="name"
                v-model="name"
                placeholder="Enter Your Name"
              />
            </div>
            <div class="form-group col-md-6">
              <label for="email"
                >Email&nbsp;<sup class="text-danger">*</sup></label
              >
              <input
                type="email"
                class="form-control"
                name="email"
                id="email"
                v-model="email"
                placeholder="Enter Your Email"
              />
            </div>
          </div>
          <div class="form-group">
            <label for="name"
              >Message&nbsp;<sup class="text-danger">*</sup></label
            >
            <textarea
              class="form-control"
              name="message"
              rows="6"
              v-model="message"
              placeholder="You Message"
            ></textarea>
          </div>
          <div class="text-center">
            <button type="submit">Send</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import Toast from "vue-toastification";
import "vue-toastification/dist/index.css";
Vue.use(Toast);
import emailjs from "emailjs-com";
export default {
  name: "Contact",
  data() {
    return {
      name: "",
      email: "",
      message: "",
    };
  },
  methods: {
    sendEmail(e) {
      if (this.name.trim() == "") {
        return this.$toast.error("Name field is required.");
      }
      if (this.email.trim() == "") {
        return this.$toast.error("Email field is required.");
      }
      if (!this.validEmail(this.email)) {
        return this.$toast.error("Valid email required.");
      }
      if (this.message.trim() == "") {
        return this.$toast.error("Message field is required.");
      }
      try {
        emailjs.sendForm(
          "service_lsycp68",
          "template_jze93jv",
          e.target,
          "user_huzNI7OGtivmrxVkkGFog",
          {
            name: this.name,
            email: this.email,
            message: this.message,
          }
        );
        this.$toast.success(
          "Thank you for your message. I'll contact you soon."
        );
      } catch (error) {
        console.log({ error });
      }
      // Reset form field
      this.name = "";
      this.email = "";
      this.message = "";
    },
    validEmail(email) {
      var re =
        /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return re.test(email);
    },
  },
};
</script>

<style>
</style>