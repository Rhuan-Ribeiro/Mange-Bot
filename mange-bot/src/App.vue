<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import FooterBot from './components/FooterBot.vue'
import Menu from './components/Menu.vue';
</script>

<template>
  <main id="card-app">
    <div id="content-app">
      <Menu />
      <RouterView /> <!--onde renderiza a pagina-->

    </div>
    <footer class="flex flex-row align-items-end justify-content-end"> 
    <!--layout flexivel, alinhar em linha, final verticalmente, final horizontalmente-->
    <div class="footer-bots flex flex-row justify-content-evenly">
      <FooterBot img="bot0.png" text="Crie seu robô com o máximo de tecnologia!"/>
      <FooterBot img="bot1.png" text="A plataforma mais amada do Brasil!"/>
      <FooterBot img="bot2.png" text="Atendimento online 24h!"/>
    </div>
    <img src="/icon2.png" id="circle">

    </footer>
  </main>

</template>

<style scoped lang="scss">
#card-app{
  width: 80%;
  height: 90%;
  background-color: var(--app-card-background);
  border-radius: 1.5rem;
  box-shadow: rgba(0, 4, 59, 0.25) 0px 50px 100px -20px, rgba(0, 0, 0, 0.3) 0px 30px 60px -30px, rgba(25, 0, 255, 0.35) 0px -2px 6px 0px inset;
}
#content-app{ 
  height: calc(100% - 10rem); //regra acima de 80% da altura total, abaixo de 80% segue o @media
}
footer{
  width: 100%;
  height: 20%;
  max-height: 10rem;
  background-color: var(--app-footer-background);
  border-radius: 0 0 1.5rem 1.5rem; //cima-dir, cima-esq, baixo-dir, baixo-esq
  .footer-bots{
    width: 80%;
    margin: auto;
  }
  #circle{
    height: 100%;
    margin-right: 1.5rem;
  }
}

@media (max-height: 880px){
  //até 80% da altura, segue essa regra:
  #content-app{
    height: 80%;
  }
}
</style>