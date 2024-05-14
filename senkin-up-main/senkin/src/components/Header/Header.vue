<script setup>

import {NavigationMenu, NavigationMenuList} from "@/components/ui/navigation-menu/index.js";
import HeaderItem from "@/components/Header/HeaderItem.vue";
import {Separator} from "@/components/ui/separator/index.js";
import LoginButton from "@/components/LoginButton/LoginButton.vue";
import {onMounted, ref} from "vue";

const routes = [
  {
    name: 'Главная',
    path: '/',
  },
  {
    name: 'Новости',
    path: '/news'
  },
  {
    name: "Объявления",
    path: '/announcements'
  },
  {
    name: 'Пользователь',
    path: '/user'
  }
]
const LOGGED = ref(false)

onMounted(() =>{
  if (localStorage.getItem('user')){
    LOGGED.value = true
  }
})
</script>

<template>
  <div>
    <div class="header w-[100dvw]">
      <router-link to="/" id="title" >NEWS</router-link>
      <navigation-menu>
        <navigation-menu-list>
          <div v-for="route in routes" :key="route.name">
            <header-item :link="route.path" :name="route.name"/>
          </div>
        </navigation-menu-list>
      </navigation-menu>
      <LoginButton id="login" v-if="LOGGED"/>
    </div>
    <separator/>
  </div>
</template>

<style scoped>
  .header {
    width: 100%;
    height: 8dvh;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
  }
  #title {
    position: absolute;
    left: 4em;
  }
  #login {
     position: absolute;
     right: 8em;
   }
  @media screen and (max-width: 768px) {
    #title {
      display: none;
    }
    #login {
      z-index: 999;
      position: absolute;
      right: 1em;
      top: 6em;
    }
  }
</style>