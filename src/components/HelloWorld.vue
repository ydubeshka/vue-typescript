<script setup lang="ts">
import {ref, reactive, type Ref} from "vue";

 const likes: Ref<number> = ref(0);
 const dislikes: Ref<number> = ref(5);

const addLike = () => likes.value++;
const addDislike = () => dislikes.value++;
</script>

<template>
  <div class="like container">
    <div>Likes count:  <strong>{{ likes }} </strong> </div>
    <button @click="addLike">like</button>
  </div>
  <div class="dislike container">
    <div>Dislikes count:  <strong>{{ dislikes }} </strong> </div>
    <button @click="addDislike">Dislike</button>
  </div>
</template>

<style scoped>

.container{
  display: flex;
  align-items: center;
  width: 20vw;
  justify-content: space-between;
  margin-bottom: 5px;
}
</style>
