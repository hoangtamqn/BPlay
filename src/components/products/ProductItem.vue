<template>
  <div class="product-card">
    <img :src="product.imgUrl" />
    <button class="button onhover">{{product.name}}</button>
    <p>{{product.description}}</p>
  </div>
</template>

<script scoped>
export default {
  props: ['product'],
};
</script>

<style>
.product-card img {
  width: 100%;
  object-fit: cover;
}

.product-card {
  text-align: center;
}

.product-card:hover {
  transition: 1.5s ease-in cubic-bezier(0.075, 0.82, 0.165, 1);
  transform: scale(0.99, 0.99);
  cursor: pointer;
}

.button {
  border: none;
  width: 100%;
  height: max(40px, 3vw);
  background: url("../../assets/images/button.png");
  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
  font-weight: bold;
  font-size: max(20px, 2vw);
  line-height: max(20px, 2vw);
  text-align: center;
  color: #fffdf1;
  margin-top: max(10px, 1vw);
  margin-bottom: max(10px, 1vw);
  white-space: nowrap;
  /* transition: 0.5 ease-in; */
}

.product-card p {
  font-size: 16px;
  text-align: center;
  color: #fffdf1;
}

.button:hover {
  /* transition: 0.5 ease-in;
  transform: translate(2px, 2px); */
  cursor: pointer;
}

@media only screen and (max-width: 768px) {
  .product-card img {
    width: 60vw;
  }
}
</style>