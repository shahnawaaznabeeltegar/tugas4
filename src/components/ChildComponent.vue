<template>
  <div class="child-component">
    <h3>Child Component</h3>
    <button @click="sendData">Kirim Data ke Parent</button>
  </div>
</template>

<script>
export default {
  name: 'ChildComponent',
  methods: {
    sendData() {
      const data = 'Halo! Saya Tegar Dari Masa Depan';
      this.$emit('send-data', data);
    }
  }
};
</script>

<style>
.child-component {
  border: 1px solid #42b983;
  padding: 10px;
  border-radius: 5px;
}

h3 {
  color: #42b983;
}

button {
  background-color: #42b983;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #358a6b;
}
</style>
