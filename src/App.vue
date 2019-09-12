<template>
  <div id="app">
   
    <SelectButtons msg="Welcome to Your Vue sanbox" :answers='answers'/>
   
  </div>
</template>

<script>
import SelectButtons from './components/SelectButtons.vue'

export default {
  name: 'app',
  components: {
    SelectButtons
  },

  data: function () {
    return {
       answers: {'answer1' : false,
                  'answer2' : false, 
                  'answer3' : false, 
                  'answer4' : false, 
                  'answer2' : false}
    }
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
