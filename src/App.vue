
<template>
  <MainView v-if="navState == 'main'" @nav-select="checkInfo"/> 
  <ManifestoView v-if="navState == 'manifesto'" @nav-select="checkInfo"/>
</template>

<script setup>
import NavBar from './components/NavBar.vue';
import MainView from "./views/MainView.vue";
import ManifestoView from "./views/ManifestoView.vue";

import { ref } from "vue";

const navState = ref("main");

function checkInfo(info) {
  navState.value = info;
}

</script>

<style scoped>

div {
  font: var(--sys-type-body-md);
}

</style>