<template>
  <div class="container">
    <div class="section-title">
      <h2>About</h2>
      <p>{{ about }}</p>
    </div>

    <div class="row">
      <div class="col-lg-4" data-aos="fade-right">
        <img src="assets/img/pro-ban.jpg" class="img-fluid" alt="" />
      </div>
      <div class="col-lg-8 pt-4 pt-lg-0 content" data-aos="fade-left">
        <h3>{{ designation }}</h3>

        <div class="row mt-5">
          <div class="col-lg-6">
            <ul>
              <li>
                <i class="bi bi-chevron-right"></i>
                <strong>Date of Birth:</strong> <span>{{ dob }}</span>
              </li>
              <li>
                <i class="bi bi-chevron-right"></i>
                <strong>Gender:</strong>
                <span>{{ gender }}</span>
              </li>
              <li>
                <i class="bi bi-chevron-right"></i>
                <strong>Mobile:</strong>
                <span>{{ mobile }}</span>
              </li>
            </ul>
          </div>
          <div class="col-lg-6">
            <ul>
              <li>
                <i class="bi bi-chevron-right"></i>
                <strong>Degree:</strong> <span>{{ degree }}</span>
              </li>
              <li>
                <i class="bi bi-chevron-right"></i>
                <strong>Email:</strong>
                <span>{{ email }}</span>
              </li>
              <li>
                <i class="bi bi-chevron-right"></i> <strong>City:</strong>
                <span>{{ city }}</span>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      about:
        "I'm Md. Shakil Hossain from Maghbazar, Dhaka. My birthplace is Raipur upazilla of Lakshmipur district. I have completed my B.Sc in CSE from Dhaka International University in 2020. I have been familiar with PHP and Laravel for over 3 years. My dream is to be a Full Stack Software Engineer and I'm working heart and soul to make my dream true. Now I am looking for a job to improve my skills and build my career.",
      designation: "Web Developer",
      dob: "1st March 1994",
      mobile: "+880 1738620241",
      email: "mdshakilhossain091@gmail.com",
      city: "Maghbazar, Dhaka, Bangladesh",
      degree: "B.Sc in CSE",
      gender: "Male",
    };
  },
};
</script>

<style>
</style>