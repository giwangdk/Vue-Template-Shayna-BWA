<template>
    <section class="women-banner spad">
        <div class="container-fluid">
            <div class="row">
                <div class="col-lg-12 mt-5" v-if="products.length>0">
                    <carousel class="product-slider" :loop="true" :dots="false" :nav="false" :items="3" :autoplay="true">
                        
                        
                        <div class="product-item" v-for="itemProduct in products" :key="itemProduct.id">
                            <div class="pi-pic">
                                <img :src="itemProduct.galleries[0].photo" alt="" />
                                <ul>
                                    <li class="w-icon active">
                                        <a href="#"><i class="icon_bag_alt"></i></a>
                                    </li>
                                    <li class="quick-view">
                                        <router-link to="/product"  href="#">+ Quick View</router-link></li>
                                </ul>
                            </div>
                            <div class="pi-text">
                                <div class="catagory-name">{{itemProduct.type}}</div>
                                <router-link to="/product">
                                    <h5>{{itemProduct.name}}</h5>
                                </router-link>
                                <div class="product-price">
                                    ${{itemProduct.price}}
                                    <span>$35.00</span>
                                </div>
                            </div>
                        </div>
                    </carousel>
                </div>

        <div class="col-lg-12" v-else>
            <p>Product Terbaru belum tersedia</p>
        </div>
            </div>
        </div>
    </section>
</template>

<script>

import carousel from "vue-owl-carousel";
import axios from 'axios';

export default {
    name:"Banner",
    components:{
        carousel,
    },
    data(){
        return{
            products:[]
        }
    },
    mounted(){
        axios
        .get("http://127.0.0.1:8000/api/products")
        .then(res=>(this.products =res.data.data.data))
        .catch(err=>console.lof(err));
        
    }
}
</script>

<style scoped>
    .product-item{
        margin-right: 25px;
    }
</style>