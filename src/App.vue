.
<template>
  <AppHeader />
  <div class="w-full flex">
    <DcHeroes />
  </div>
</template>

<script>
import "./assets/tailwind.css";
import AppHeader from "./components/AppHeader.vue";
import DcHeroes from "./components/DcHeroes.vue";

export default {
  components: { AppHeader, DcHeroes },
  
};
</script>

<style></style>
