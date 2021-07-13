<template>
  <header class="hero-container">
    <img class="hero-BG" src="../assets/images/banner.png" />
    <div class="hero-wrapper">
      <p class="title">
        CASINO<br />PLAYGAME
      </p>
      <div class="scroll">
        <div class="btn-playgame onhover">
          <h5>Scroll</h5>
          <img src="../assets/images/scroll-down.svg" />
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
};
</script>

<style scoped>
.hero-container {
  position: relative;
  z-index: 1;
}

.hero-container .title {
  font-style: normal;
  font-weight: 800;
  font-size: max(30px, 5vw);
  text-align: center;
  letter-spacing: 10px;
  mix-blend-mode: normal;
  text-shadow: 0px 0px 50px rgba(0, 0, 0, 0.4);
  background: -webkit-linear-gradient(#ffffff, #ffecbc);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  padding-top: max(130px, 24vw);
  animation: fadeUp 1000ms forwards;
  opacity: 0;
}

.hero-container .scroll {
  text-align: center;
  padding-top: max(70px, 9vw);
  animation: arrowLoop 600ms forwards;
  animation-delay: 400s;
  animation-iteration-count: infinite;
}

.hero-container .scroll h5 {
  color: #ffffff;
  margin-bottom: 5px;
  font-size: max(16px, 1.2vw);
}

.hero-container .scroll img {
  width: max(20px, 2.5vw);
}

.hero-container .scroll .btn-playgame {
  width: fit-content;
  margin: auto;
}

.hero-container .hero-BG {
  position: absolute;
  left: 0px;
  top: 0px;
  z-index: 0;
  width: 100%;
  min-height: 300px;
}

.hero-container .hero-wrapper {
  position: relative;
}
</style>