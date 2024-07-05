<template>
    <div>
      <div class="drop-area" v-drop:drop.prevent="onDrop">
        <p>Drag items here</p>
      </div>
      <div class="items">
        <div v-for="item in items" :key="item.id" v-drag:drag="item">{{ item.name }}</div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        items: [
          { id: 1, name: 'Item 1' },
          { id: 2, name: 'Item 2' },
        ]
      };
    },
    methods: {
      onDrop(event) {
        console.log('Item dropped', event);
      }
    }
  };
  </script>
  
  <style>
  .drop-area {
    border: 2px dashed #ccc;
    padding: 20px;
    margin: 20px;
  }
  .items div {
    border: 1px solid #000;
    padding: 10px;
    margin: 5px;
    cursor: grab;
  }
  </style>
  