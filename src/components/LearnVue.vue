<template>
  <div class="hello" @mouseover="updateXy">
    {{ msg }}
    <h2>{{ dem }}</h2>
    <h1>{{ dem > 20 ? "lon hon 20" : "nho hon 20" }}</h1>
    <button @click="update">dem</button>
    <p>toa do : {{ x }} - {{ y }}</p>
    <input v-model="todo" type="text" />
    <button @click="addTodo()">them</button>
    <div class="" v-for="(todo, index) in todos" :key="index">
      <p>{{ todo.name }}</p>
      <p>{{ todo.status }}</p>
      <button @click="deleteTodo(index)">xoa</button>
      <button>sua</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "LearnVue",
  data() {
    return {
      dem: 1,
      x: 0,
      y: 0,
      todo: "",
      todos: [
        {
          name: "ngyenvinh",
          status: "an",
        },
        {
          name: "nguyenvinh",
          status: "hien",
        },
      ],
    };
  },
  props: {
    msg: String,
  },
  methods: {
    update() {
      this.dem++;
    },
    updateXy(event) {
      (this.x = event.clientX), (this.y = event.clientY);
    },
    addTodo() {
      if (this.todo.length === 0) return;
      this.todos.push({ name: this.todo, status: "an" });
      this.todo = "";
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
