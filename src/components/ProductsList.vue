<template>
  <div class="prod-list" v-if="products.length">
    <div v-for="product of products" :key="product._id">
      <ProductCard :product="product" />
    </div>
  </div>
  <div v-else>
    Loading..
  </div>
</template>

<script>
import ProductCard from "../components/ProductCard.vue";
export default {
  name: "ProductsList",
  components: {
    ProductCard,
  },
  props: ["products"],
  data() {
    console.log(this.products);

    return {};
  },
};
</script>

<style>
.prod-list {
  width: 100%;
  overflow: auto;
  display: flex;
  flex-wrap: nowrap;
  background-color: transparent;
}

/* width */
::-webkit-scrollbar {
  width: 0.8em;
}

/* Track */
::-webkit-scrollbar-track {
  border-radius: 1em;
}

/* Handle */
::-webkit-scrollbar-thumb {
  border-radius: 1em;
  background: #222e506b;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #222e50c2;
}
</style>
