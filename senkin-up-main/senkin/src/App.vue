<script setup>
import Header from "@/components/Header/Header.vue";
import {Toaster} from "@/components/ui/sonner/index.js";
</script>
<template>
  <div class="overflow-x-hidden">
    <Header/>
    <router-view/>
    <Toaster/>
  </div>
</template>


<style scoped>

</style>