<template>
 <div>
   <p>
     {{ title }}

   </p>
   <input type="text" v-model="todo" >
   <br>
   <button @click="handleAddTodo">Save todo</button>
 </div>

</template>
<script lang="ts">
import {reactive, ref} from 'vue';

export default {
  setup(props: any, {emit}: any) {
    const state = reactive({
      title: "Add todo"
    })
    const todo = ref("");
    return {
      title: state.title,
      todo,
      handleAddTodo() {
        emit("ops:todo:add",todo.value);
      }
    }
  }
}
</script>
