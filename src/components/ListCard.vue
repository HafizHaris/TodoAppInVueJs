<template>
  <div class="list">
    <div
      v-for="(todo, index) in todos"
      :key="index"
      :class="`todo-item ${todo.done && 'done'}`"
    >
      <label>
        <input type="checkbox" v-model="todo.done" />
        <span :class="`bubble ${todo.category}`"></span>
      </label>

      <div class="todo-content">
        <input type="text" v-model="todo.content" />
      </div>

      <div class="actions">
        <button class="delete" @click="removeTodo(todo)">
          Delete
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["todos"],
  methods: {
    removeTodo(todo) {
        this.$emit('removeTodo',todo)
    },
  },
};
</script>
