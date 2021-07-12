<template>
  <section id="about-us">
    <div class="wrapper">
      <div class="info">
        <div class="title">
          <h5>BPLAY GAME</h5>
          <h3>WHO WE ARE?</h3>
        </div>
        <div class="subtitle">
          <p>
            BPlay was founded in 2015 by a group of highly skilled professionals with over 15 years of experience in
            the iGaming industry. Today we are an international company with more than 100 employees and have
            operations in Malta, Ukraine, Romania, Norway, India, Myanmar and Taiwan...
          </p>
        </div>
      </div>
      <div class="experience">
        <div class="text-box">
          <h1>15</h1>
          <h2>YEARS</h2>
          <hr class="line" />
          <p>
            of experience
            <br />in the
            <span>iGaming</span>
          </p>
        </div>
      </div>
      <div class="pad"></div>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style scoped>
#about-us {
  background: url(../assets/images/About/maps.png), url(../assets/images/About/buildings-near-body-of-water-2837909.png);
  background-repeat: no-repeat, no-repeat;
  background-position: top center, bottom center;
  background-size: 120vw, 130vw;
  position: relative;
  margin-top: max(110px, 9vw);
}

.pad {
  padding: 37vw 0px;
}
.wrapper {
  height: max(1400px, 50%);
  position: relative;
}

.info {
  text-align: center;
}

.subtitle {
  padding-top: 32px;
}

.subtitle p {
  max-width: 824px;
  margin: auto;
}

.map-background {
  padding-top: max(160px, 8vw);
  z-index: 2;
  width: 100%;
}

.experience {
  margin-top: -100px;
  z-index: 1;
}

.experience .background {
  width: 100%;
  min-width: 1200px;
}

.experience .text-box {
  position: absolute;
  padding: 0 max(40px, 3vw) max(40px, 3vw);
  left: 0px;
  top: 45vw;
  background: rgba(21, 22, 30, 0.9);
  border-radius: 0px 0px 20px 20px;
}

.experience .text-box h1 {
  font-weight: bold;
  font-size: max(100px, 10vw);
  line-height: max(100px, 10vw);
  text-align: center;
  color: #f41616;
}

.experience .text-box h2 {
  font-size: max(50px, 4vw);
  line-height: max(50px, 4vw);
  text-align: center;
  color: #ffffff;
}

.experience .line {
  border: 0;
  background-color: red;
  height: 1px;
  width: 100px;
  margin-left: auto;
  margin-right: auto;
  margin-top: 20px;
}

.experience .text-box p {
  font-size: 30px;
  line-height: 38px;
  text-align: center;
  color: #ffffff;
}

.experience .text-box p span {
  color: red;
}

@media only screen and (max-width: 768px) {
  #about-us {
    background-position: center center, bottom center;
    min-height: 140vw;
  }
  .experience .text-box {
    left: 50%;
    top: 85vw;
    transform: translateX(-50%);
  }

  .experience .text-box h1 {
    font-weight: bold;
    font-size: max(80px, 8vw);
    line-height: max(80px, 8vw);
  }

  .experience .text-box h2 {
    font-size: max(40px, 3vw);
    line-height: max(40px, 3vw);
  }

  .experience .text-box p {
    font-size: 22px;
    line-height: 22px;
  }
}
</style>