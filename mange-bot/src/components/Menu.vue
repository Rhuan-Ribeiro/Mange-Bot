<script setup lang="ts">

</script>

<template>
    <header class="flex flex-row align-items-center justify-content-start">
        <img src="/icon-robots.png" alt="">
        <nav class="ml-5">
          <RouterLink class="m-4" to="/">Home</RouterLink> <!--atalhos, linka a url como o botão do cabeçalho (header) -->
          <RouterLink class="m-4" to="/cart">Cart</RouterLink>
          <RouterLink class="m-4" to="/build">Build</RouterLink>
        </nav>
    </header>
</template>

<style scoped lang="scss">
header {
    height: 5rem;
    width: 40rem;
    
    img {
        margin-left: 4rem;
        height: 4rem;
    }

    a {
        text-decoration: none;
        font-size: 1.5rem;
        color: var(--app-dark-text-color);
        position: relative;
        
        &::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: -1px; // ajuste a posição conforme necessário
            width: 100%;
            height: 1px;
            background-color: var(--app-dark-text-color);
            transform: scaleX(0);
            transform-origin: bottom right;
            transition: transform 0.3s ease-in-out;
        }
        
        &:hover::after {
            transform: scaleX(1);
            transform-origin: bottom left;
        }
    }

    .router-link-exact-active {
        font-weight: bold;
    }
}
</style>