<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import CalculatorRefactored from './components/CalculatorRefactored.vue'
import Todos from './components/Todos.vue'
</script>

<template>
  <div>
    <div class="wrapper">
      <!-- <HelloWorld msg="You did it!" /> -->

      <!-- <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav> -->
      <Todos />
      <!-- <CalculatorRefactored/> -->
    </div>
  </div>

  <!-- <RouterView /> -->
</template>

<style scoped>

</style>
