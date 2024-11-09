<template>
    <div>
      <input v-model="newItem" @keyup.enter="addItem" placeholder="添加 TODO">
      <ul>
        <li v-for="(item, index) in items" :key="index">
          {{ item }}
          <button @click="removeItem(index)">删除</button>
        </li>
      </ul>
    </div>
  </template>
   
  <script>
  export default {
    data() {
      return {
        newItem: '',
        items: ['学习', '编程', '乐趣']
      };
    },
    methods: {
      addItem() {
        if (this.newItem.trim()) {
          this.items.push(this.newItem.trim());
          this.newItem = '';
        }
      },
      removeItem(index) {
        this.items.splice(index, 1);
      }
    }
  };
  </script>