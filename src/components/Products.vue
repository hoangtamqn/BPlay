<template>
  <section id="products">
    <div class="wrapper" id="playgame">
      <div class="info">
        <div class="left">
          <h5>BPLAY GAME</h5>
          <h3>OUR PRODUCTS</h3>
        </div>
        <div class="right">
          <p>BPlay’s high quality iGaming Platform offers a complete solution for your casino. Get the full White Label turnkey solution or the Seamless API with our comprehensive selection of games. Through our global network of premium partners such as Vivo Gaming, SBTech and HoGaming you will have access to the best Live Casino, Sportsbook, Slots, Table Games, Number Games and Fishing Games on the market.</p>
        </div>
      </div>
      <div class="sp">
        <carousel :settings="settings">
          <slide v-for="product in products" :key="product.id">
            <ProductItem :product="product"/>
          </slide>

          <template #addons>
            <pagination />
          </template>
        </carousel>
      </div>
      <div class="pc">
        <div class="list-product">
          <ProductItem v-for="product in products" :key="product.id" :product="product"/>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
// import $ from "jquery";
import ProductItem from "./products/ProductItem.vue";
import 'vue3-carousel/dist/carousel.css';
import { Carousel, Slide, Pagination } from 'vue3-carousel';

export default {
  components: {
    ProductItem,
    Carousel,
    Slide,
    Pagination,
    // Navigation,
  },
  data() {
    return {
      products: [
        {
          id: 1,
          imgUrl: require("@/assets/images/products/product-1.png"),
          name: "Live Casino",
          description: "Vivo LiveCasino, HoGaming Live Casino, BPlay LiveCasino"
        },
        {
          id: 1,
          imgUrl: require("@/assets/images/products/product-2.png"),
          name: "Fishing Game",
          description: "BPlay Fishing 2D, BPlay Fishing 3D"
        },
        {
          id: 1,
          imgUrl: require("@/assets/images/products/product-3.png"),
          name: "Sport Book",
          description: "BTI Sportsbook, BPlay Sportsbook"
        },
        {
          id: 1,
          imgUrl: require("@/assets/images/products/product-4.png"),
          name: "Quick Number",
          description: "Keno, Number Games, Lottery"
        },
        {
          id: 1,
          imgUrl: require("@/assets/images/products/product-5.png"),
          name: "White Label",
          description: "White Label"
        },
        {
          id: 1,
          imgUrl: require("@/assets/images/products/product-6.png"),
          name: "Slots",
          description: "BPlay Slots, Jackpot Slots"
        },
        {
          id: 1,
          imgUrl: require("@/assets/images/products/product-7.png"),
          name: "Seamless API",
          description: "Seamless API"
        },
        {
          id: 1,
          imgUrl: require("@/assets/images/products/product-8.png"),
          name: "Full Package",
          description: "Full Package"
        },
        {
          id: 1,
          imgUrl: require("@/assets/images/products/product-9.png"),
          name: "Table Game",
          description: "Table Game"
        }
      ],
      mobile: false,
      settings: {
        itemsToShow: 1.3,
        snapAlign: 'left',
      },
    };
  }
};
</script>

<style scoped>
#products {
  background: url("../assets/images/products/product-backgroud-2.png"), url("../assets/images/products/product-backgroud.png");
  background-repeat: no-repeat, no-repeat;
  background-position: top center, top center;
  background-size: 100vw, cover;
  padding-top: 237px;
  padding-bottom: 120px;
}

.info {
  display: flex;
}

.info .right {
  margin-left: 5vw;
}

.list-product {
  padding-top: 83px;
}

.list-product {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 48px 48px;
  margin-bottom: 42px;
}

.list-product-mobile {
  display: flex;
  overflow: auto;
}

.list-product-mobile .item {
  padding: 10px;
  display: block;
}

::ng-deep.carousel__pagination-button, .carousel__pagination-button--active {
  background: darkgreen;
}
@media only screen and (max-width: 768px) {
  .info {
    display: block;
  }
}
</style>