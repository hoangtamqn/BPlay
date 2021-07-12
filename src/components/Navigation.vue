<template>
  <div>
    <div v-if="!mobile">
      <DesktopNav :menus="menus" @clickMenu="clickMenu($event)"/>
    </div>
    <div v-else>
      <MobileNav :menus="menus" @clickMenu="clickMenu($event)"/>
    </div>
  </div>
</template>

<script>
import DesktopNav from "./navigation/DesktopNav";
import MobileNav from "./navigation/MobileNav.vue";

export default {
  name: "Navigation",
  components: {
    DesktopNav,
    MobileNav
  },
  data() {
    return {
      mobile: false,
      windowWidth: null,
      activeMenu: null,
      menus: [
        {id: 1, name: 'ABOUT US', url: '#about-us', actived: true},
        {id: 2, name: 'PRODUCTS', url: '#products', actived: false},
        {id: 3, name: 'PARTNERS', url: '#partners', actived: false},
        {id: 4, name: 'OUR CLIENT', url: '#our-client', actived: false},
        {id: 5, name: 'CONTACT US', url: '#contact-us', actived: false},
      ]
    };
  },
  created() {
    window.addEventListener("resize", this.checkScreen);
    this.checkScreen();
  },
  methods: {
    clickMenu(event) {
      this.menus.map((item => {
        if (item.actived) {
          item.actived = false;
          return item;
        }
      }));

      this.menus.map((item => {
        if (item.id === event.id) {
          item.actived = true;
          return item;
        }
      }));
    },
    checkScreen() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth <= 1080) {
        this.mobile = true;
        return;
      }
      this.mobile = false;
      return;
    },
  }
};
</script>

<style scoped>
</style>