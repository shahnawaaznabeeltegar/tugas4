<template>
  <div id="app">
    <h1>Components</h1>
    <ParentComponent @show-data="displayData">
    </ParentComponent>
    <div v-if="dataFromChild" class="data-display">
      <h2>Data from Child Component:</h2>
      <p>{{ dataFromChild }}</p>
      <button class="reset-button" @click="resetData">Reset Data</button>
    </div>
  </div>
</template>

<script>
import ParentComponent from './components/ParentComponent.vue';

export default {
  name: 'App',
  components: {
    ParentComponent
  },
  data() {
    return {
      dataFromChild: null
    };
  },
  methods: {
    displayData(data) {
      this.dataFromChild = data;
    },
    resetData() {
      this.dataFromChild = null;
    }
  }
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  text-align: center;
  margin-top: 50px;
}

h1 {
  color: #42b983;
}

.data-display {
  margin-top: 20px;
  padding: 10px;
  border: 2px solid #42b983;
  border-radius: 5px;
}

button {
  background-color: #42b983;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  margin-top: 10px;
}

button:hover {
  background-color: #358a6b;
}

.reset-button {
  background-color: #e74c3c;
}

.reset-button:hover {
  background-color: #c0392b;
}
</style>
