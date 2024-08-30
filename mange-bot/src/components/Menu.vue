<script setup lang="ts">
import { changeLanguage, type AvailableLanguages, i18nApplication } from '@/i18n/i18n';
import { type Ref, ref, computed } from 'vue';

const currentLanguage: Ref<AvailableLanguages> = 
    ref(i18nApplication.global.locale.value);

const change = ()=> {
    if(currentLanguage.value == 'br'){
        changeLanguage('en');        
    }
    else{
        changeLanguage('br');
    }
    currentLanguage.value = i18nApplication.global.locale.value;
}
const flag = computed(()=> currentLanguage.value == 'br'?  'br.png' : 'en.png');

</script>

<template>
    <header class="flex flex-row align-items-center justify-content-start">
        <!-- <img src="/icon-robots.png" alt="robot logo"> -->
        <RouterLink to="/"><img src="/robot-icon-2.png" alt="robot logo"></RouterLink>
        <nav class="ml-5">
          <RouterLink class="m-4" to="/">{{ $t('MENU.HOME') }}</RouterLink>
          <RouterLink class="m-4" to="/cart">{{ $t('MENU.CART') }}</RouterLink>
          <RouterLink class="m-4" to="/build">{{ $t('MENU.BUILD') }}</RouterLink>
        </nav>
        <img id="flag" :src="flag" alt="flag" @click="change">
    </header>
</template>

<style scoped lang="scss">
    header{
        height: 5rem;
        width: 40rem;
        position: relative;
        img{
            margin-left: 4rem;
            height: 4rem;
        }
        a{
            text-decoration: none;
            font-size: 1.5rem;
            color: var(--app-dark-text-color);
        }
        .router-link-exact-active{
            font-weight: bold;
        }
        #flag{
          position: absolute;
          right: 2.5rem;

          height: 2.5rem;  
          width: 3.5rem;
          cursor: pointer;
          border-radius: 0.5rem;
        }
    }
</style>