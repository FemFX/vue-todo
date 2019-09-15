<template>
  <section id="todos">
    <div class="todo" v-for="(todo) in todos" v-bind:key="todo.id">
      <input type="checkbox" name="done" v-if="todo.done" checked />
      <input type="checkbox" name="done" v-else />
      <label for="done">{{ todo.name }}</label>
      <button class="remove" v-on:click="() => removeTodo(todo.id)">Remove</button>
    </div>
  </section>
</template>
<script>
export default {
  name: "Todos",
  props: ["todos"],
  methods: {
    removeTodo: function(id) {
      this.$emit("removeTodo", id);
    }
  }
};
</script>
<style scoped>
#todos {
  display: flex;
  flex-direction: row;
  justify-content: center;
  flex-wrap: wrap;
  width: 100%;
}
#todos .todo {
  width: 24%;
  margin: 15px;
  padding: 15px;
  background: #fff;
  display: flex;
}
#todos .todo label {
  flex: 1;
}
button {
  border: none;
  background: #ea2027;
  color: #fff;
  border-radius: 5%;
  cursor: pointer;
  outline: none;
}
</style>