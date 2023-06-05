<template>
  <h1>{{ title }}</h1>
  <br>
  <SignupForm/>
</template>


<script>
import SignupForm from './components/SignupForm.vue'

export default {
  name: 'App',   
  components: {
    SignupForm
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
    margin-top: 5px;
  }

  h1 {
    border-bottom: 1px solid #ddd;
    display: inline-block;
    padding-bottom: 10px;
  }

</style>
