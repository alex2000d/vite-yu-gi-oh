<script>
import { store } from '../store.js'

export default {
    data(){
    return{
      store,
    }
  }

}
</script>
<template>
    <div class="py-4 mx-3 main">
        <div class="py-4 mx-5">
            <select class="form-select" style="width: 16rem;" aria-label="Default select example">
                <option selected>alien</option>
                <option value="1">One</option>
                <option value="2">Two</option>
                <option value="3">Three</option>
              </select>
        </div>
        <div class="container bg-white p-5">
            <div class="row">
                <div class="col-12">
                    <div class="container bg-dark">
                        <div class="row">
                            <div class="col-12">
                                <p class="text-white mt-3">found 39 card</p>
                                
                            </div>
                        </div>
                    </div>
                    <div class="container">
                        <div class="row row-cols-5">
                          <div class="col" v-for="card in store.cardlist">
                              <div class="card me-3" style="width: 14rem;">
                                  <img :src="card.card_images[0].image_url" class="card-img-top">
                                  <div class="card-body">
                                    <h5 class="card-title">{{card.name}}</h5>
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
</style>