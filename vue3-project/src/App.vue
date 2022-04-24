<template>
  <div class="name">{{name}}</div>

  <input type="text" v-model="name">
  <button class="btn btn-primary" @click="clickedEvent">Click</button>
</template>

<script>
import {ref} from 'vue';

export default {
  setup() {
    const name = ref('Taehyung Kim Code!');

    const clickedEvent = () => {
      // name.value = 'Clicked';
    };

    return {
      name,
      clickedEvent,
    };
  },
}
</script>

<style>
.name{
  color:#ff0000;
}
</style>