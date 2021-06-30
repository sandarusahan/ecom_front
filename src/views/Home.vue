<template>
  <div class="home">
    <div class="products-lists">
      <div class="products-list animate__animated animate__fadeInLeft">
        <h3>Featured Products</h3>
        <ProductsList :products="products" />
      </div>
      <div class="products-list animate__animated animate__fadeInLeft delay-1">
        <h3>For you</h3>
        <ProductsList :products="products" />
      </div>
      <div class="products-list animate__animated animate__fadeInLeft delay-2">
        <h3>Viewed</h3>
        <ProductsList :products="products" />
      </div>
    </div>
  </div>
</template>

<script>
import ProductCard from "../components/ProductCard.vue";
import ProductsList from "../components/ProductsList.vue";
import SearchBar from "../components/SearchBar.vue";

import { ref } from "vue";

export default {
  name: "Home",
  components: {
    ProductCard,
    ProductsList,
    SearchBar,
  },
  setup() {
    const products = ref([]);
    const error = ref(null);

    const load = async () => {
      try {
        let productsRes = await fetch("http://localhost:4000/api/product");
        if (!productsRes.ok) {
          throw Error("Error fetching data");
        }

        products.value = await productsRes.json();
      } catch (err) {
        error.value = err.message;
        console.log(error.value);
      }
    };

    load();

    return { products, error };
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
.home {
  width: 100%;
  display: flex;

  justify-content: center;
}

.products-lists {
  width: 100%;
}
.products-list {
  margin: 1em 1em 0 1em;
  padding: 1em;
  text-align: start;
  color: var(--secondary1);
  font-size: 1.3rem;
  background: rgb(38, 120, 202);
  border-radius: 0.4em;
}

.delay-1 {
  animation-delay: 0.25s;
}
.delay-2 {
  animation-delay: 0.5s;
}
</style>
