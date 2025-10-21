<template>
  <Local_ex01 />

  <hr />
  <div class="container">
    <Review_01 />
    <hr />
    <Login />
  </div>
</template>

<script setup>
import Local_ex01 from "./components/Local_ex01.vue";
import Login from "./components/Login.vue";
import Review_01 from "./components/Review_01.vue";
</script>

<style scoped>
.container {
  display: flex;
}
</style>
