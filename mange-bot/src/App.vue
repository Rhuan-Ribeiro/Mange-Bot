<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>   
  <main id="card-app">
    <div id="content-app">
      <header>
        <nav>
          <RouterLink to="/">Home</RouterLink>
          <RouterLink to="/cart">Cart</RouterLink>
          <RouterLink to="/build">Build</RouterLink>
        </nav>
      </header>

      <RouterView /> 
    </div>
    <footer>

    </footer>
  </main>

</template>


<style scoped lang="scss">
#card-app {
    height: 90%;
    width: 80%;
    background-color: var(--app-card-background);
    border-radius: 1.5rem;
    box-shadow: rgba(0, 0, 0, 0.16) 0px 10px 36px 0px, rgba(0, 0, 0, 0.06) 0px 0px 0px 1px;
}

</style>
