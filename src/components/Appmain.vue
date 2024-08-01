<script>
import { store } from '../store.js'

export default {
    data(){
    return{
      store,
    }
  },
methods:{
    sendarchetype(){

    }
}
}
</script>
<template>
    <div class="py-4 mx-3 main">
        <div class="py-4 margin">
            <select class="form-select text-dark" style="width: 16rem;">
                <option v-for="archetype in store.typesarrey">{{archetype}}</option>
              </select>
        </div>
        <div class="container bg-white p-5">
            <div class="row">
                <div class="col-12">
                    <div class="container bg-dark">
                        <div class="row">
                            <div class="col-12">
                                <p class="text-white mt-3"> found {{store.cardlist.length}} cards</p>
                                
                            </div>
                        </div>
                    </div>
                    <div class="container">
                        <div class="row row-cols-5">
                          <div class="col" v-for="card in store.cardlist">
                              <div class="card me-3" style="width: 14rem;">
                                  <img :src="card.card_images[0].image_url" class="card-img-top">
                                  <div class="card-body">
                                    <h5 class="card-title text-white">{{card.name}}</h5>
                                    <p class="card-text">{{ card.archetype }}</p>
                                  </div>
                              </div>
                          </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
    </div>
</template>
<style lang="scss">
    .main{
        background-color: orange;
    }

    .card-body{
        background-color: rgb(213, 136, 2);
        height: 120px;
    }

    .margin{
        margin-left: 60px;
    }
</style>