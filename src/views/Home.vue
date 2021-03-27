<template>
 <div id="app">
   <div class="list">
     <p class="title">Todo list</p>
     
     <Todo @getChildText="showChildText"></Todo>
     <p v-for="(item,index) in textList" :key="index" class="todolist">{{item}}
       <button @click="deleteTodo(item)" class="delete">削除</button>
     </p>
   </div>
 </div>
</template>

<script>
import Todo from "../components/Todo.vue";
export default {
  data() {
    return {
      textList: []
    };
  },
  methods: {
    showChildText(childText) {
      this.textList.push(childText);
    },
    deleteTodo: function(item) {
      this.textList.splice(item, 1);
    }
  },
  components: {
    Todo
  }
};
</script>

<style scoped>
#app {
  background-color: navy;
  position: relative;
  height: 100vh;
  width: 100vw;
}
.list {
  background-color: white;
  width: 50vw;
  padding: 30px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  border-radius: 10px;
}
.title {
  color: black;
  font-weight: bold;
  font-size: 28px;
}
.todolist {
  color: black;
  width: 30%;
  padding: 10px;
  border-radius: 5px;
  border: 1px solid gray;
  font-size: 14px;
  outline: none;
}
.delete {
  color: greenyellow;
  border: solid greenyellow;
  background-color: white;
  font-size: 12px;
  font-weight: bold;
  padding: 8px 18px;
  border-radius: 5px;
  cursor: pointer;
  outline: none;
}
</style>