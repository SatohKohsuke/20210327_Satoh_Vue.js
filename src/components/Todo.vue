<template>
  <div class="todo">
    <input type="text" v-model="childText" class="input-tsuika"/>
    <button @click="sendParent" class="button-tsuika">追加</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      childText: ""
    };
  },
  methods: {
    sendParent() {
      this.$emit("getChildText", this.childText);
      this.childText = "";
    }
  }
};
</script>

<style scoped>
.input-tsuika {
  color: black;
  width: 80%;
  padding: 5px;
  border-radius: 5px;
  border: 1px solid gray;
  font-size: 14px;
  outline: none;
}
.button-tsuika {
  color: pink;
  border: solid pink;
  background-color: white;
  font-size: 12px;
  font-weight: bold;
  padding: 8px 18px;
  border-radius: 5px;
  cursor: pointer;
  outline: none;
}
</style>