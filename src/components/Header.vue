<template>
  <header>
    <input type="text" name="todo" id="todo" v-model="todoValue" placeholder="Your Todo" />
    <button id="createTodo" class="submit" @click="createTodo">+</button>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      todoValue: ""
    };
  },
  methods: {
    createTodo: function() {
      if (this.todoValue) {
        this.$emit("createTodo", this.todoValue);
        this.todoValue = "";
      }
    }
  }
};
</script>
<style scoped>
header {
  display: flex;
}
header input {
  flex: 1;
  height: 50px;
  box-sizing: border-box;
  text-indent: 15px;
  font-size: 20px;
}
header input {
  outline: none;
}
header .submit {
  width: 50px;
  height: 50px;
  color: #171717;
  font-size: 28px;
  line-height: 1;
  font-weight: 700;
  background-color: #ffce00;
  border: none;
  outline: none;
  cursor: pointer;
}
header .submit:hover {
  background-color: #ffd833;
}
header .submit:active {
  background-color: #e6b900;
}
</style>