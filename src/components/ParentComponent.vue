<template>
    <div class="parent-component">
      <h2>Parent Component</h2>
      <ChildComponent @send-data="emitDataToParent" />
      <div class="slot-content">
        <slot name="extra-content"></slot>
      </div>
    </div>
  </template>
  
  <script>
  import ChildComponent from './ChildComponent.vue';
  
  export default {
    name: 'ParentComponent',
    components: {
      ChildComponent
    },
    methods: {
      emitDataToParent(data) {
        this.$emit('show-data', data);
      }
    }
  };
  </script>
  
  <style>
  .parent-component {
    border: 2px solid #35495e;
    padding: 20px;
    margin: 20px;
    border-radius: 10px;
  }
  
  h2 {
    color: #35495e;
  }
  
  .slot-content {
    margin-top: 10px;
    padding: 10px;
    border-top: 1px solid #ccc;
  }
  </style>
  