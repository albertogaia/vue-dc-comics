<template>
    <div class="my-content">
        <div class="jumbotron">
            <img src="@/assets/img/jumbotron.jpg" alt="jumbotron">
        </div>
        <div class="container">
            <div class="current-series">
                <span class="section-title">CURRENT SERIES</span>
            </div>
            <div class="dc-products">
                <ProductCard 
                v-for="(product, index) in products"
                :key="index"
                :prod="product"
                />
                <button>LOAD MORE</button>
            </div>
        </div>
        
    </div>
</template>

<script>
import ProdItems from '@/assets/data/DCComics.js'
import ProductCard from '@/components/ProductCard.vue'
export default {
    name: 'Products',
    components: {
        ProductCard,
    },
    data(){
        return{
            products: ProdItems,
        }
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

        @include button(colored);
    }
}


</style>