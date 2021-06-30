<template>
  <div class="card">
    <div class="details">
      <div class="name">
        <h3>{{ product.name }}</h3>
      </div>
      <div class="price">
        <h4>{{ product.price }}</h4>
      </div>
      <div class="buttons">
        <button class="btn">Add to cart</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: ["product"],
  data() {
    return {};
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
.card {
  position: relative;
  width: 9em;
  height: 13em;
  margin: 0.8em;
  border-radius: 8px;
  background: var(--secondary4);
  box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.9);
  text-align: center;
}
.card:hover {
  transform: scale(1.02);
  box-shadow: 6px 6px 16px rgba(0, 0, 0, 0.9);
}
.details {
  width: 100%;
  position: absolute;
  bottom: 0;
  justify-content: center;
  padding: 0.5em;
  color: var(--secondary5);
  font-size: 1rem;
}
.in-cart {
  transform: scale(0.95);
}

.out-of-stock {
  filter: grayscale(100%);
  transform: scale(0.9);
}
</style>
