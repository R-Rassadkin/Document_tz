<template>
  <div>
    <document
      :name="name">
      </document>
  </div>
</template>

<script>
import document from './components/document'

export default {
  name: 'App',
   data(){
     return{
       name:'FIO'
     }
   },
   components:{
     document
   }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
