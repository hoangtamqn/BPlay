<template>
  <div>
    <div class="pc">
      <DesktopNav :menus="menus" @clickMenu="clickMenu($event)"/>
    </div>
    <div class="sp">
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
  mounted() {
    this.mobile = this.isMobile();
    window.addEventListener("resize", this.checkScreen);
    this.checkScreen();
    console.log("ddd", this.mobile);
  },
  computed: {
    // mobile
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
      console.log(this.windowWidth);
      if (this.windowWidth <= 1080) {
        this.mobile = true;
        return;
      }
      this.mobile = false;
      console.log(this.mobile);
      return;
    },
    isMobile() {
      if(/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)) {
        return true
      } else {
        return false
      }
    }
  }
};
</script>
<style scoped>
</style>