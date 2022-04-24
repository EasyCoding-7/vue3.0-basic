<template>
  <div class="name">{{name.id}}</div>

  <button class="btn btn-primary" v-on:click="clickedEvent">Click</button>
</template>

<script>
import {reactive} from 'vue';

export default {
  setup() {
    // const name = ref('Taehyung Kim Code!');
    const name = reactive({
       id: 1
      });

    const fn = () => {
      return 'HelloWorld';
    };

    const fn2 = (n) => {
      return 'HelloWorld2 ' + n;
    };

    const clickedEvent = () => {
      name.id = 2;
    };

    return {
      name,
      fn,
      fn2,
      clickedEvent
    };
  },
}
</script>

<style>
.name{
  color:#ff0000;
}
</style>