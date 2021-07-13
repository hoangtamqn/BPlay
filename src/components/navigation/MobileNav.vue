<template>
  <header :class="{'nav-background': showBackground, 'mobile-nav-bg': mobileNav}">
    <nav class="wrapper">
      <div v-if="!mobileNav" class="navigation">
        <div class="branding">
          <a href="#">
            <img src="../../assets/images/Logo.svg" alt />
          </a>
        </div>
        <div class="right-menu">
          <div class="language">
            <img src="../../assets/images/flag-en.svg" />
            <span>EN</span>
            <img class="arrow" src="../../assets/images/arrow-down.svg" />
          </div>
          <div class="icon-mobile">
            <img @click="toggleMobileNav" src="../../assets/images/icon-bars.png" />
          </div>
        </div>
      </div>
      <div v-else class="navigation-nav">
        <div class="language">
          <img src="../../assets/images/flag-en.svg" />
          <span>EN</span>
          <img class="arrow" src="../../assets/images/arrow-down.svg" />
        </div>
        <div class="icon-mobile">
          <img @click="toggleMobileNav" src="../../assets/images/icon-close.png" />
        </div>
      </div>
      <transition>
        <ul v-show="mobileNav" class="dropdown-nav">
          <li v-for="menu in menus" :key="menu.id">
            <a
              :href="menu.url"
              :class="{'active': menu.actived}"
              @click="clickMenu(menu)"
            >{{menu.name}}</a>
          </li>
        </ul>
      </transition>
    </nav>
  </header>
</template>

<script >
export default {
  props: ["menus"],
  data() {
    return {
      mobileNav: false,
      showBackground: false,
    };
  },
  created() {
    window.addEventListener("scroll", this.scrollUpdateHeaderBG);
    this.scrollUpdateHeaderBG();
  },
  methods: {
    clickMenu(menu) {
      this.$emit("clickMenu", menu);
      this.mobileNav = false;
    },
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav;
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
  width: 100vw;
  position: fixed;
  z-index: 99;
  color: #ffffff;
  transition: 0.5 ease all;
}

nav {
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
  margin-left: min(50px, 3vw);
  animation: fadeToLeft 800ms forwards;
  opacity: 0;
}

.mobile-nav-bg {
  background: var(--dark-color-4);
  overflow-y: scroll;
  height: 100vh;
}

.navigation, .navigation-nav {
  height: 128px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.dropdown-nav {
  list-style: none;
  padding: 0px;
  height: 100vh;
}

.dropdown-nav li {
  height: 128px;
  text-align: center;
  margin: 0px 50px;
  border-bottom: 0.8px solid rgba(255, 255, 255, 0.1);
}

.dropdown-nav li a {
  text-decoration: none;
  line-height: 128px;
}

.dropdown-nav li a.active {
  color: var(--red-color);
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

.navigation-nav .language {
  animation: fadeToRight 800ms forwards;
  opacity: 0;
}

nav .language:hover {
  border: 1px solid var(--red-color);
  cursor: pointer;
}

nav .language:hover .arrow{
  opacity: 0.5;
}

nav .icon-mobile:hover {
  cursor: pointer;
}
</style>