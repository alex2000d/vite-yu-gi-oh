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
      this.getcardlist(),
      this.gettypesarrey()
  },
  methods:{
       getcardlist(){
        if(store.archetypestatus != ''){
          store.apiurl += `&archetype=${store.archetypestatus}`
        }
        axios.get(store.apiurl).then((result)=>{
          store.cardlist = result.data.data
        })
       },
       gettypesarrey(){
        axios.get(store.apiurltypes).then((result)=>{
          for (let i=0; i < 10; i++){
            store.typesarrey.push(result.data[i].archetype_name)
          }
        });
       }
  },

  data(){
      return{
        store,
      }
  }
}
</script>
<template lang="">
  <div>
    <Appheader />
    <Appmain @filter="getcardlist"/>
  </div>
</template>
<style lang="scss">
 @import "../src/styles/generals.scss"
</style>
