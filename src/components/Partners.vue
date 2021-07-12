<template>
  <section id="partners">
    <div class="wrapper">
      <div class="pc">
        <div class="mobile-wrapper">
          <div class="left">
            <img src="../assets/images/Partners/partner-image.png" alt />
          </div>
          <div class="right">
            <div class="info">
              <h5>BPLAY GAME</h5>
              <h3>PARTNERS</h3>
              <p>As a BPlay client you will benefit from content from more than 20 top tier providers. Based on your casino’s concept and targeted markets, we will tailor the perfect portfolio of games to offer to your players.</p>
            </div>
            <div class="list-partner-logo">
              <img src="../assets/images/Partners/sbtech.png" alt />
              <img src="../assets/images/Partners/iovation.png" alt />
              <img src="../assets/images/Partners/seon.png" alt />
              <img src="../assets/images/Partners/hogaming.png" alt />
              <img src="../assets/images/Partners/vivo.png" alt />
            </div>
          </div>
        </div>
      </div>
      <div class="sp">
        <div class="right">
          <div class="info">
            <h5>BPLAY GAME</h5>
            <h3>PARTNERS</h3>
            <p>As a BPlay client you will benefit from content from more than 20 top tier providers. Based on your casino’s concept and targeted markets, we will tailor the perfect portfolio of games to offer to your players.</p>
          </div>
          <div class="list-partner-logo">
            <img src="../assets/images/Partners/sbtech.png" alt />
            <img src="../assets/images/Partners/iovation.png" alt />
            <img src="../assets/images/Partners/seon.png" alt />
            <img src="../assets/images/Partners/hogaming.png" alt />
            <img src="../assets/images/Partners/vivo.png" alt />
          </div>
        </div>
        <div class="left">
          <img src="../assets/images/Partners/partner-image.png" alt />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style scoped>
#partners {
  background: url("../assets/images/Partners/partner-bg.png");
  background-repeat: no-repeat;
  background-position: left;
  padding: 10vw 0px;
  background-size: max(400px, 50%);
}

.mobile-wrapper {
  display: flex;
  text-align: left
}

.left img {
  margin-right: 60px;
  width: 40vw;
}

.list-partner-logo {
  text-align: center;
}

.list-partner-logo img {
  width: max(110px, 10vw);
}

.info p {
  padding-top: 8px;
}

.info h3 {
  padding-top: 16px;
}

@media only screen and (max-width: 768px) {
  #partners {
    background-position: left bottom;
    padding: 10vw 0px;
    background-size: max(400px, 70%);
  }

  .left img {
    margin-right: 0px;
    margin-top: 5vw;
    width: 47vw;
  }

  .right,
  .left {
    text-align: center;
  }

  /* .sp {
    display: none;
  } */
}
</style>