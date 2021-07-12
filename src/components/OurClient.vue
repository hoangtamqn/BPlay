<template>
  <section id="our-client">
    <div class="wrapper">
      <div class="info">
        <h5>BPLAY GAME</h5>
        <h3>OUR CLIENTS</h3>
      </div>
      <div class="list-client-logo">
        <img src="../assets/images/Client/9.png" alt />
        <img src="../assets/images/Client/12.png" alt />
        <img src="../assets/images/Client/16.png" alt />
        <img src="../assets/images/Client/bet365.png" alt />
        <img src="../assets/images/Client/betfair.png" alt />
        <img src="../assets/images/Client/betway.png" alt />
        <img src="../assets/images/Client/bwin.png" alt />
        <img src="../assets/images/Client/williamhill.png" alt />
        <img src="../assets/images/Client/1.png" alt />
        <img src="../assets/images/Client/2.png" alt />
        <img src="../assets/images/Client/5.png" alt />
        <img src="../assets/images/Client/6.png" alt />
      </div>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style scoped>
#our-client {
  text-align: center;
}

.list-client-logo {
  padding-top: 80px;
  display: grid;
  grid-template-columns: repeat(auto-fill, 14vw);
  align-content: center;
  grid-gap: 5vw 3vw;
  margin-bottom: 42px;
  justify-content: center;
}
.list-client-logo img {
  width: -webkit-fill-available;
}

@media only screen and (max-width: 768px) {
  .our-client-wrapper {
    margin: 0 3vw;
  }

  .list-client-logo {
    grid-template-columns: repeat(auto-fill, 22vw);
    grid-gap: 15px 15px;
  }
}
</style>