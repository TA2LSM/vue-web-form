<template>
  <h1>{{ title }}</h1>
  <br>

  
</template>


<script>
// import Block from './components/Block.vue'
// import Results from './components/Results.vue'


export default {
  name: 'App',   
  components: {

  },

  data() {
    return {
      title: "~ Vue Web Form  ~",

    }
  },

  methods: {

  },
}
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #444;
    margin-top: 60px;
  }

  h1 {
    border-bottom: 1px solid #ddd;
    display: inline-block;
    padding-bottom: 10px;
  }

  button {
    width: 15 0px;
    background-color: #0faf87;
    color: white;
    border: none;
    padding: 8px, 16px;
    border-radius: 4px;
    font-size: 16px;
    letter-spacing: 1px;
    cursor: pointer;
    margin: 10px;
  }

  button[disabled] {
    opacity: 0.2;
    cursor: not-allowed;
  }
</style>
