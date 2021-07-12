<template>
  <header :class="{'nav-background': showBackground, }">
    <nav class="wrapper">
      <div class="branding">
        <a href="#">
          <img src="../../assets/images/Logo.svg" alt />
        </a>
      </div>

      <ul class="navigation">
        <li v-for="menu in menus" :key="menu.id">
          <a
            :href="menu.url"
            :class="{'active': menu.actived}"
            @click="clickMenu(menu)"
          >{{menu.name}}</a>
        </li>
      </ul>
      <div class="language">
        <img src="../../assets/images/flag-en.svg" />
        <span>EN</span>
        <img class="arrow" src="../../assets/images/arrow-down.svg" />
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  props: ["menus"],
  data() {
      return {
          showBackground: false
      }
  },
  created() {
    window.addEventListener("scroll", this.scrollUpdateHeaderBG);
    this.scrollUpdateHeaderBG();
  },
  methods: {
    clickMenu(menu) {
      this.$emit("clickMenu", menu);
    },
    scrollUpdateHeaderBG() {
        var scroll = window.scrollY;
        if (scroll >= 100) {
            this.showBackground = true;
        } else {
            this.showBackground = false;
        }
    }
  },
  deactivated() {
      window.removeEventListener('scroll', this.scrollUpdateHeaderBG);
  },
};
</script>

<style scoped>
header {
  width: 100%;
  position: fixed;
  z-index: 99;
  color: #ffffff;
  transition: 0.5 ease all;
}

nav {
  height: 128px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  margin: 0 auto;
  animation: fadeDown 1000ms forwards;
  opacity: 0;
}

nav .right-menu {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav .icon-mobile {
  margin-left: 50px;
}

nav .navigation {
  display: flex;
  list-style: none;
  align-items: center;
  padding: 0px;
}

nav .navigation li {
  margin: 0 20px;
}

nav .navigation li:nth-last-of-type(1) {
  margin-right: 50px;
}

nav .navigation li a {
  text-decoration: none;
  color: var(--light-color);
  position: relative;
  font-style: normal;
  font-weight: bold;
  font-size: 16px;
  line-height: 128px;
  letter-spacing: 1px;
}

nav .navigation li a:hover {
  opacity: 0.5;
}

nav .navigation li a.active::after {
  content: "";
  position: absolute;
  height: 3px;
  width: 100%;
  background: var(--red-color);
  left: 0;
  bottom: -14px;
}

nav .language {
  display: flex;
  width: 130px;
  height: 48px;
  color: var(--light-color);
  border: 1px solid #ffffff;
  box-sizing: border-box;
  border-radius: 100px;
  align-items: center;
  line-height: 48px;
  font-weight: bold;
  justify-content: space-around;
}

nav .language:hover {
  border: 1px solid var(--red-color);
  cursor: pointer;
}

nav .language:hover .arrow{
  opacity: 0.5;
}

@media only screen and (max-width: 1260px) {
  nav .navigation li {
    margin: 0 10px;
  }

  nav .navigation li:nth-last-of-type(1) {
    margin-right: 2vw;
  }
}
</style>