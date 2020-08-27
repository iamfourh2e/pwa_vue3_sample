<template>
  <div class="home">
    <todo></todo>
    <add-todo @ops:todo:add="handleTodoAdd"></add-todo>

  </div>
</template>

<script lang="ts">
  import Todo from '@/components/Todo.vue';
  import AddTodo from '@/components/AddTodo.vue';
  import {ref} from 'vue';
  export default {
    components: {
      Todo,
      AddTodo
    },
    setup() {
      const comp = ref("todo");

      return {
        comp,
        handleSwitch() {
          if (comp.value === 'todo') {
            comp.value = 'add-todo';
          }else{
            comp.value = 'todo';
          }
        },
        handleTodoAdd(val: any) {
          console.log(val);
        }
      }
    }
  }
</script>
