<template>
  <div class="search-bar">
    <input
      type="text"
      name="search-input"
      id="searchInput"
      class="search-input"
      placeholder="Search products..."
      aria-label="search"
    />
    <button>
      Search
    </button>
  </div>
</template>

<script>
export default {};
</script>

<style>
body {
  display: flex;
  justify-content: center;
  align-items: center;
  background: var(--clr-bg);
}

.search-bar {
  position: relative;
  width: 60px;
  height: 60px;
  background: var(--clr-body);
  border-radius: 60px;
}
</style>
