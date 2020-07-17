<template>
    <section class="women-banner spad">
        <div class="container-fluid">
            <div class="row">
                <div class="col-lg-12 mt-5" v-if="products.length > 0">
                    <carousel class="product-slider"  :autoplay="true" :items="3" :dots="false" :nav="false">>
                        <div class="product-item" v-for="productItem in products" v-bind:key="productItem.id">
                            <div class="pi-pic">
                                   <img v-bind:src="productItem.galleries[0].photo" alt="" />
                                <ul>
                                    <li class="w-icon active">
                                        <a href="#"><i class="icon_bag_alt"></i></a>
                                    </li>
                                     <li class="quick-view">
                                         <router-link to="/product">+ Quick View</router-link>
                                    </li>
                                </ul>
                            </div>
                            <div class="pi-text">
                                <div class="catagory-name">{{productItem.type}}</div>
                                <router-link to="/product">
                                <a href="#">
                                    <h5>{{productItem.name}}</h5>
                                </a></router-link>
                                <div class="product-price">
                                   {{productItem.price}}
                                    <span>{{productItem.price}}</span>
                                </div>
                            </div>
                        </div>
                       
                    </carousel>
                </div>

                <div class="col-lg-12" v-else>
                    <p>Product Terbaru Belum Tersedia</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import carousel from 'vue-owl-carousel'
import axios from 'axios'

export default {  
    name:'bannerSyana',
      components:{
         carousel
     },
     data(){
         return{
             products:[]
         }
     },
     mounted(){
         axios.get('http://shayna-backend.belajarkoding.com/api/products')
         .then(res=>(this.products = res.data.data.data))
         .catch(err=>console.log(err));
     }
}
</script>

<style scoped>
    .product-item{
        margin-right: 25px;
    }
</style>