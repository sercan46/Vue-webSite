<template>
      <footer id="footer">
      <div class="container">
        <h3>{{about.companyName}}</h3>
        <p>
          Et aut eum quis fuga eos sunt ipsa nihil. Labore corporis magni
          eligendi fuga maxime saepe commodi placeat.
        </p>
        <div class="social-links">
          <a :href="about.twitter" target="_blank" class="twitter"><i class="bx bxl-twitter"></i></a>
          <a :href="about.facebook" target="_blank"  class="facebook"><i class="bx bxl-facebook"></i></a>
          <a :href="about.instagram" target="_blank"  class="instagram"><i class="bx bxl-instagram"></i></a>
          <a :href="about.linkedin" target="_blank"  class="linkedin"><i class="bx bxl-linkedin"></i></a>
        </div>
        <div class="copyright">
          &copy; Copyright <strong><span></span></strong
          >. All Rights Reserved
        </div>
        <div class="credits">
          <!-- All the links in the footer should remain intact. -->
          <!-- You can delete the links only if you purchased the pro version. -->
          <!-- Licensing information: https://bootstrapmade.com/license/ -->
          <!-- Purchase the pro version with working PHP/AJAX contact form: https://bootstrapmade.com/green-free-one-page-bootstrap-template/ -->
          Designed by <a href="https://www.sercanozbek.com">Sercan Ozbek</a>
        </div>
      </div>
    </footer>
</template>
<script>
export default {
 data() {
    return {
     
      aboust: [],
      about: {
        companyMail: "",
        companyName: "",
        companyPhone: "",
        facebook: "",
        instagram: "",
        password: "",
        twitter: "",
        userName: "",
        userPhone: "",
        localation: "",
      }
    };
  },
  methods:{
        getUserData() {
      this.$http
        .get("https://eticaret-de184-default-rtdb.firebaseio.com/about.json")
        .then((resp) => {
          let aboutData = resp.data;
          for (let key in aboutData) {
            this.aboust.push({ id: key, about: aboutData[key] });
          }
          this.aboust.forEach((x) => {
            this.aboutData = x.about;
          });
          this.about = this.aboutData.about;
        });
    },
  },
    mounted() {
    this.getUserData();
  },
  
}
</script>