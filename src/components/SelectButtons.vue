<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div   ref="test" :key="i" v-for="(answer, i) in Object.keys(this.$props.answers)">
      <button class="btn"
          :class="[isActive[i] ? 'active' : '']"
          @click="setActive(answer)"
          :value="answers[i]"
          :key="i"
          > {{answer}} 
      </button>
    </div>
    <h1> Computed Properties </h1>
    <h2>{{isActive}}</h2>
    <h2>{{indexesOfTrue}}</h2>
    <h2>{{valuesOfTrue}}</h2>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    answers: Object
  },

  methods: {
    setActive: function(e){
      this.$props.answers[e] = !this.$props.answers[e]
    },
  },

  computed: {
    isActive: function(){
      return Object.values(this.$props.answers)
    },

    indexesOfTrue: function(){
      let arr = Object.values(this.$props.answers)
      let val = true 
      var indexes = [], i = -1;
      while ((i = arr.indexOf(val, i+1)) != -1){ indexes.push(i);}
      return indexes;
    },

    valuesOfTrue: function(){
      let arr = this.$props.answers
      var result = {};
      for (var key in arr) {
          if (arr[key] === true) {
              result[key] = true;
          }
      }
      return result
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.active{
  padding: 2em;
  background-color: green
}

.btn{
  padding: 2em;
}

</style>
