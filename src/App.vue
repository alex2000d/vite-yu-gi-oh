<script>
import { store } from './store.js'
import axios from 'axios';
import Appheader from './components/Appheader.vue';
import Appmain from './components/Appmain.vue';
export default {
  components:{
   Appheader,
   Appmain,
  },
  created(){

  },
  methods:{
       getcardlist(){
        axios.get(store.apiurl).then((result)=>{
          // store.cardlist =
        })
       }
  },

  data(){
      return{
        store
      }
  }
}
</script>
<template lang="">
  <div>
    <Appheader />
    <Appmain />
  </div>
</template>
<style lang="scss">
 @import "../src/styles/generals.scss"
</style>
