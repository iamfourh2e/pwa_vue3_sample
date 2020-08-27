<template>
  <p>
    {{title}}

  </p>
  <p>Display todo list</p>
  <ul>
    <li v-for="(todo,i) in todoList" :key="i">
      {{todo}}
    </li>
  </ul>
</template>

<script lang="ts">
import {ref, onMounted} from 'vue';
export default {
  setup() {
    const title = ref("Todo");
    const todoList = ref([]);
    onMounted(() => {
        title.value = "Todo is mounted"
    })

    return {
      title,
      todoList
    }
  }
}
</script>
