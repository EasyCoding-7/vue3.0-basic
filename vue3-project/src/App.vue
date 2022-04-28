<template>
<!-- class="container" - 좌/우 여백을 둔다 -->
    <div class="container">
    <h2>To-Do List</h2>
    <form  
      @submit.prevent="onSubmit"
      class="d-flex"
    ><!-- .prevent - submit 후 화면의 갱신을 막는다 -->
      <div class="flex-grow-1 mr-2"> <!-- mr-2 - margin right -->
        <input
          class="form-control"
          type="text" 
          v-model="todo"
          placeholder="Type new to-do"
        >
      </div>
      <div>
        <button 
          class="btn btn-primary"
          type="submit"
        >
          Add
        </button>
      </div>
    </form>
    {{ todos }}
  </div>
</template>

<script>
import {ref} from 'vue';

export default {
  setup() {
    const todo = ref('');
    const todos = ref([]);

    const onSubmit = () => {
      todos.value.push({
        id: Date.now(),
        subject: todo.value
      });
    };

    return {
      todo,
      todos,
      onSubmit,
    };
  },
}
</script>

<style>
.name{
  color:#ff0000;
}
</style>