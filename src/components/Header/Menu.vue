<template>
  <div>
    <div id="topbar" class="d-none d-lg-flex align-items-center fixed-top">
      <div class="container d-flex">
        <div class="contact-info mr-auto">
          <i class="icofont-envelope"></i>
          <a :href="'mailto:' + about.companyMail">{{ about.companyMail }}</a>
          <i class="icofont-phone"></i>
          <a :href="'tel:' + about.companyPhone">
            {{ about.companyPhone }}
          </a>
        </div>
        <div class="social-links">
          <a :href="about.twitter" target="_blank" class="twitter"
            ><i class="icofont-twitter"></i
          ></a>
          <a :href="about.facebook" target="_blank" class="facebook"
            ><i class="icofont-facebook"></i
          ></a>
          <a :href="about.instagram" target="_blank" class="instagram"
            ><i class="icofont-instagram"></i
          ></a>
          <a :href="about.linekdin" target="_blank" class="linkedin"
            ><i class="icofont-linkedin"></i
          ></a>
        </div>
      </div>
    </div>

    <header id="header" class="fixed-top">
      <div class="container d-flex align-items-center">
        <a href="index.html" class="logo mr-auto"
          ><img src="/src/assets/img/about.png" alt="" class="img-fluid"
        /></a>
        <h1 class="logo mr-auto">
          <a href="index.html">{{ about.companyName }}</a>
        </h1>

        <nav class="nav-menu d-none d-lg-block">
          <ul style="font-weight:bold">
            <li class="active"><a href="index.html"> <i class="icofont-check-alt"></i
          > Anasayfa</a></li>
            <li><a href="#about"><i class="icofont-check-alt"></i
          >Hakkımızda</a></li>
            <li><a href="#whywe"><i class="icofont-check-alt"></i
          >Neden Biz</a></li>
            <li><a href="#product"><i class="icofont-check-alt"></i
          >Ürünlerimiz</a></li>
            <li><a href="#chef"><i class="icofont-check-alt"></i
          >Ustalarımız</a></li>
            <li><a href="#contact"><i class="icofont-check-alt"></i
          >İletişim</a></li>
          </ul>
        </nav>
        <!-- <a href="#about" class="get-started-btn scrollto">Get Started</a> -->
      </div>
    </header>
    <!-- End Header -->

    <!-- ======= Hero Section ======= -->
    <section>
     <div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel"  data-interval="5000">
  <ol class="carousel-indicators">
    <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
    <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
    <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
  </ol>
  <div class="carousel-inner" >
    <div class="carousel-item active">
      <img class="d-block w-100" src="/src/assets/img/slide/slide-1.jpg" alt="First slide">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" src="/src/assets/img/slide/slide-2.jpg" alt="Second slide">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" src="/src/assets/img/slide/slide-3.jpg" alt="Third slide">
    </div>
  </div>
  <a class="carousel-control-prev" href="#carouselExampleIndicators" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleIndicators" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>
</div>
    </section>
    <!-- End Hero -->
  </div>
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
      },
    };
  },
  methods: {
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
};
</script>
<style scoped>
.carousel-inner>.carousel-item {
    -webkit-transition: -webkit-transform 1.2s ease-in-out !important;
    -o-transition: -o-transform 1.2s ease-in-out !important;
    transition: transform 1.2s ease-in-out !important;
}
</style>