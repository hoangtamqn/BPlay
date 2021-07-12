<template>
  <div>
    <Navigation />
    <Hero />
    <AboutUs />
    <Products />
    <Partners />
    <OurClient />
    <Footer />
  </div>
</template>

<script>
import $ from "jquery";
import Navigation from "./components/Navigation";
import Hero from "./components/Hero.vue";
import AboutUs from "./components/AboutUs.vue";
import Products from "./components/Products.vue";
import Partners from "./components/Partners.vue";
import OurClient from "./components/OurClient.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    Navigation,
    Hero,
    AboutUs,
    Products,
    Partners,
    OurClient,
    Footer
  },
  mounted() {
    $(window).scroll(this.scrollFunction);
    $('.btn-playgame').click(function() {
      $('html, body').stop().animate({
        scrollTop: $("#playgame").offset().top
      }, 1000);
    });
    $('#btnTop').click(function() {
        $('html, body').stop().animate({
            scrollTop: 0
        }, 1000);
    });
  },
  methods: {
    scrollFunction() {
      if (document.body.scrollTop > 100 || document.documentElement.scrollTop > 100) {
        $("#btnTop").show();
      } else {
        $("#btnTop").hide();
      }
    }
  },
};
</script>

<style>
:root {
  --dark-color-1: #333646;
  --dark-color-2: #252734;
  --dark-color-3: #1a1c25;
  --dark-color-4: #15161e;
  --light-color: #fdfdfd;
  --red-color: #ff3232;
  --carousel-color-primary: #ff3232;
  --carousel-color-secondary: #c78282;
}

html {
  scroll-behavior: smooth;
}

* {
  margin: 0;
  box-sizing: border-box;
}

body {
  font-family: "Roboto", sans-serif;
  letter-spacing: 1px;
  background: var(--dark-color-4);
}

.wrapper {
  width: 85%;
  margin: 0px auto;
}

.nav-background {
  background-color: rgba(0, 0, 0, 0.8);
}

.info h5 {
  font-size: max(15px, 1.5vw);
  line-height: max(15px, 1.5vw);
  letter-spacing: 10px;
  color: #ff3232;
  white-space: nowrap;
}

.info h3 {
  font-weight: 800;
  font-size: max(30px, 3vw);
  line-height: max(30px, 3vw);
  color: #fdfdfd;
  padding-top: 8px;
  white-space: nowrap;
}

.info p {
  font-weight: normal;
  font-size: 16px;
  line-height: 30px;
  letter-spacing: 1px;
  color: #eaeaea;
}

.custom-sel {
  display: inline-block;
  align-self: flex-start;
}

.custom-sel a {
  text-decoration: none;
  text-transform: uppercase;
  margin: 0;
  padding: 10px;
  text-align: left;
  color: white;
  font-size: 15px;
  font-weight: 700;
  line-height: 24px;
  display: block;
}

.custom-sel a:hover {
  text-decoration: none;
  background-color: #edf0f2;
  color: #546e7a;
}

.custom-sel a.selected {
  background-color: transparent;
}

.custom-sel a.selected:hover {
  background-color: transparent;
  color: #546e7a;
}

.hidden {
  display: none !important;
}

.onhover:hover{
  opacity: 0.5;
  cursor: pointer;
}

.show-sel {
  background-color: #000000;
  box-shadow: -5px 0px 65px 0px rgba(0, 0, 0, 0.18);
}

.pc {
  display: block;
}

.sp {
  display: none;
}

@keyframes fadeDown {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

@keyframes fadeToRight {
  from {
    opacity: 0;
    transform: translateX(-100px);
  }

  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeToLeft {
  from {
    transform: translateX(30px);
  }

  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes rotate {
  from {
    transform: rotate(360deg);
  }
  to {
    transform: rotate(0deg);
  }
}

@keyframes arrowLoop {
  from {
    transform: translateY(-5px);
  }

  to {
    /* opacity: 1; */
    transform: translateY(5px);
  }
}

.carousel__pagination {
  display: flex;
  justify-content: center;
  list-style: none;
  padding-top: 20px;
}
.carousel__pagination-button {
  margin: 10px;
  width: 10px;
  height: 10px;
  border: 0;
  cursor: pointer;
  padding: 0px;
  background: #505153;
  transform: rotate(45deg);
}

.carousel__pagination-button--active {
  background: #F41616;
}

@media only screen and (max-width: 768px) {
  .pc {
    display: none;
  }

  .sp {
    display: block;
  }

  .info p {
    text-align: center;
    margin: 20px 0;
  }
  .info h5,
  .info h3 {
    text-align: center;
  }
}
</style>
