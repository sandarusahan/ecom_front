<template>
  <div id="nav" class="animate__animated animate__backInDown">
    <router-link to="/">Home</router-link> |
    <router-link to="/categories">Categories</router-link> |
    <router-link to="/about">About</router-link>
  </div>
  <router-view />
</template>

<style>
#app {
  width: 100%;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#nav {
  padding: 1.2em;
  font-size: 1.6rem;
  text-align: center;
}

#nav a {
  font-weight: bold;
  color: var(--secondary2);
}

#nav a.router-link-exact-active {
  color: var(--secondary1);
}
</style>
