<script setup lang="ts">
import {ref, reactive, type Ref} from "vue";

const count = 10;
const counterState = {
  _value: count,
  get value() {
    return this._value
  },
  set value(newValue: number) {
    this._value = newValue
  }
}




</script>

<template>
  <div class="counter-container">
    {{ counterState.value }}
  </div>
  <button>Add</button>
  <button> Reset</button>
</template>

<style scoped>
.counter-container {
  width: 100%;
  height: 20%;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px;
  border-radius: 10px;

}
.container{
  display: flex;
  align-items: center;
  width: 20vw;
  justify-content: space-between;
  margin-bottom: 5px;
}
</style>
