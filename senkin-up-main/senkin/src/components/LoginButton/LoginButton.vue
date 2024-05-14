<script setup>

import {ref} from "vue";
import {Button} from "@/components/ui/button/index.js";
const user = ref(null)

</script>

<template>
  <RouterLink to="/auth">
    <Button variant="outline" v-if="!user">Вход</Button>
  </RouterLink>
</template>

<style scoped>

</style>