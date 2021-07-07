<template>
  <div>
    <ul>
      <Todoitem 
        v-for="(todo, i) in todos" 
        :todo="todo" 
        :index="i"
        :key="todo.id"
        @remove-todo="removeTodo"/>
    </ul>
  </div>
</template>


<script>
import Todoitem from '@/components/Todoitem'
export default {
  props: ['todos'],
  components : {
    Todoitem
  },
  methods: {
    removeTodo(id) {
      this.$emit('remove-todo', id)
    }
  }
}
</script>

<style scoped>
  ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }
</style>