<script setup lang="ts">

import TheNavigation from "./components/TheNavigation.vue";
import TheHeader from "./components/TheHeader.vue";
import TheTimeline from "./pages/TheTimeline.vue";
import TheActivities from "./pages/TheActivities.vue";
import TheProgress from "./pages/TheProgress.vue";
import {PAGE_TIMELINE, PAGE_ACTIVITIES, PAGE_PROGRESS} from './constants';
import {ref} from "vue";

const currentPage = ref(normalizePageHash());
function normalizePageHash () {
  const hash = window.location.hash.slice(1);


  if([PAGE_TIMELINE, PAGE_ACTIVITIES, PAGE_PROGRESS].includes(hash)) {
    return hash
  }
  window.location.hash = PAGE_TIMELINE
  return PAGE_TIMELINE
}
</script>

<template>
  <TheHeader />

  <main class="flex flex-grow flex-col">
    <TheTimeline v-show="currentPage === PAGE_TIMELINE"/>
    <TheActivities v-show="currentPage === PAGE_ACTIVITIES"/>
    <TheProgress  v-show="currentPage === PAGE_PROGRESS"/>
  </main>

  <TheNavigation :current-page="currentPage" @navigate="currentPage = $event" />
  </template>

<style >
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
