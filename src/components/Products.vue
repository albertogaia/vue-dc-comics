<template>
    <div class="my-content">
        <div class="jumbotron">
            <img :src="require(`@/assets/${jumbo[0].img}`)" :alt="jumbo[0].altText">
        </div>
        <div class="container">
            <div class="current-series">
                <span class="section-title">CURRENT SERIES</span>
            </div>
            <div class="dc-products">
                <ProductCard 
                component-to-re-render
                v-for="(product, index) in products"
                :key="index"
                :prod="product"
                />
            </div>
            <button>LOAD MORE</button>

        </div>
        
    </div>
</template>

<script>
import ProdItems from '@/assets/data/DCComics.js'
import ProductCard from '@/components/ProductCard.vue'
import Jumbotron from '@/assets/data/Jumbotron.js'
export default {
    name: 'Products',
    components: {
        ProductCard,
    },
    data(){
        return{
            products: ProdItems,
            jumbo: Jumbotron,
        }
    },
    methods:{

    },
    mounted(){

    }
    
}
</script>

<style scoped lang="scss">
@import '@/style/general.scss';

.my-content{
    background-color: $secondary-color;
    
    .jumbotron{
        height: 350px;

        img{
            height: 100%;
            width: 100%;
            object-position: top;
            object-fit: cover
        };
    }

    .current-series{
        position: absolute;
        align-self: flex-start;
        top: -20px;
        display: inline-block;
        height: 40px;
        width: max-content;
        @include center(vertical);

        background-color: $primary-color;
        padding: 0px 15px;
        color: $txt-light;
        font-size: $fs-lg;
    }

    .dc-products{
        @include center(horizontal);
        flex-wrap: wrap;
        padding: 50px 0px;
    }
    
    .container{
        display: flex;
        flex-direction: column;
        align-items: center;
        button{
            width: max-content;
            margin-bottom: 30px;
        }
        @include button(colored);

    }

}


</style>