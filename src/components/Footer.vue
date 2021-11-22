<template>
  <footer id="footer">
    <div class="wrapper">
      <div id="contact-us">
        <img src="../assets/images/Logo.svg" alt />
        <div class="info">
          <h4>CONTACT US</h4>
          <p>
            <img src="../assets/images/icon-location.png" alt="">&nbsp;&nbsp;2901 Marmora Road, Glassgow, Seattle, WA 98122-1090
          </p>
          <p>
            <img src="../assets/images/icon-mail.png" alt="">&nbsp;&nbsp;info@bplay.com
          </p>
        </div>
      </div>
      <hr class="footer-line" />
      <div class="copyright">
        <div class="logo pc">
          <img src="../assets/images/Footer/license.png" alt />
          <img src="../assets/images/Footer/sabs-1.png" alt />
          <img src="../assets/images/Footer/curacao-1.png" alt />
          <img src="../assets/images/Footer/itech-1.png" alt />
        </div>
        <div class="logo sp">
          <img src="../assets/images/Footer/sabs-1.png" alt />
          <img src="../assets/images/Footer/curacao-1.png" alt />
          <img src="../assets/images/Footer/itech-1.png" alt />
          <br />
          <img src="../assets/images/Footer/license.png" alt />
        </div>
        <hr class="sp footer-line" />
        <p>Copyright © 2020 bplay.com. All rights reserved.</p>
        <button @click="saveFile">Save File</button>
      </div>
    </div>
    <div id="btnTop" class="btn-top onhover">
        <img src="../assets/images/scroll-down.svg">
        <h5>Top</h5>
    </div>
  </footer>
</template>

<script>
import { saveAs } from "file-saver-ios-bugfix";
export default {
  methods: {
    saveFile() {
      saveAs(
        "https://dev05.px123.info/qrcode/xyz/dt/img/d6a0598bea87af9bb82da85fc99df4a6.png",
        "QR-code.png"
      );
    }
  }
};
</script>

<style scoped>
#footer {
    background: url("../assets/images/Footer/Mask\ Group.png");
    background-repeat: no-repeat;
    background-position: top;
    background-size: cover;
    margin-top: -100px;
    padding-top: 28vw;
    width: 100vw;
}

#contact-us {
    display: flex;
    justify-content: space-between;
}

.info {
    margin: auto 20px;
}

.info h4{
    color: #FDFDFD;
    white-space: nowrap;
    padding: 8px;
}

.info p {
    display: flex;
    align-self: center;
    padding: 10px;
}

.info p img {
    width: 23px;
    height: 25px;
}

hr.footer-line{
    border: 0;
    background-color: #252734;
    height: 2px;
    margin-left: auto;
    margin-right: auto;
    margin: 20px 0;
}

.copyright{
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
}

.copyright .logo img{
    padding-right: 20px;
}

.copyright p{
    color: white;
    margin-top: auto;
    margin-bottom: auto;
    font-size: 14px;
}

.btn-top{
    display: none;
    position: fixed;
    bottom: 20px;
    right: 30px;
    z-index: 99;
    border: none;
    outline: none;
    color: white;
    cursor: pointer;
    padding: 15px;
    border-radius: 10px;
    font-size: 18px;
    animation: arrowLoop 600ms forwards;
    animation-delay: 400s;
    animation-iteration-count: infinite;
}

.btn-top h5{
    font-size: max(16px, 1.2vw);
}

.btn-top img{
    width: max(20px, 2.5vw);
    display: block;
    margin: auto;
    -webkit-transform:rotate(180deg);
    -moz-transform: rotate(180deg);
    -ms-transform: rotate(180deg);
    -o-transform: rotate(180deg);
    transform: rotate(180deg);
}

@media only screen and (max-width: 768px) {
  .footer-wrapper {
    margin: 0 3vw;
  }
  .info {
    margin: 20px auto;
  }
  .info p {
    text-align: left;
  }

  #contact-us {
    display: block;
  }

  .copyright {
    display: block;
  }

  .copyright .logo {
    margin: auto;
    width: fit-content;
  }

  .copyright .logo img {
    margin: 10px;
  }
}
</style>
