<template>
  <div id="app">
    <todoapp></todoapp>
    <button @click="getData">
        make Get
    </button>

    <button @click="setData">
      Post 
    </button>
  </div>
</template>

<script>
  import todoapp from './components/todoapp.vue'
  export default {
    name: 'App',
    components: {
      todoapp
    },
    methods: {
      getData() {
        fetch("http://127.0.0.1:5000/api/v1/test")
          .then(res => res.json)
          .then(console.log)
          .catch(console.error);
      },
      setData() {
        fetch("http://127.0.0.1:5000/api/v1/test", { method: "POST" })
          .then(res => res.json)
          .then(console.log)
          .catch(console.error);
      }
    }
  }
</script>