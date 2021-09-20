<template>
    <div class="footer">
        <div class="footer-top">
            <div class="container">
                <div class="top-left p-tb">
                    <div class="col">
                        <ul class="list-link"><span class="title-list">DC COMICS</span>
                            <li v-for="(link, index) in footDCComics" :key="index"><a href="">{{link.text}}</a></li>
                        </ul>
                        <ul class="list-link"><span class="title-list">SHOP</span>
                            <li v-for="(link, index) in footShop" :key="index"><a href="">{{link.text}}</a></li>
                        </ul>
                    </div>
                    <div class="col">
                        <ul class="list-link"><span class="title-list">DC</span>
                            <li v-for="(link, index) in footDC" :key="index"><a href="">{{link.text}}</a></li>
                        </ul>
                    </div>
                    <div class="col">
                        <ul class="list-link"><span class="title-list">SITES</span>
                            <li v-for="(link, index) in footSites" :key="index"><a href="">{{link.text}}</a></li>
                        </ul>
                    </div>
                    
                </div>
                <div class="top-right">
                    <img src="../assets/img/dc-logo-bg.png" alt="Logo DC">
                </div>
            </div>
        </div>
        <div class="footer-bottom p-tb">
            <div class="container">
                <div class="sign-up">

                </div>
                <div class="socials">

                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Links from '@/assets/data/Links.js'
export default {
    name: 'Footer',
    data(){
        return{
            footDCComics : Links.footDCComics,
            footShop : Links.footShop,
            footDC : Links.footDC,
            footSites : Links.footSites,
        }
    }
}
</script>

<style scoped lang="scss">
@import '@/style/general';

.p-tb{
    padding: 20px 0px;
}

.list-link{
    color: #c7c7c7; 
    font-size: 12px; 
    list-style: none;
    margin: 15px 0px;
    a {
        text-decoration: none;
        line-height: 20px;
        color: inherit;

        &:hover{
            color: $primary-color;
        }
    }

    .title-list{
        display: block;
        margin-bottom: 15px;
        color: white; 
        font-size: 18px; 
        font-weight: 600; 
    }
}

.footer-top{
    height: 400px;
    background-image: url('../assets/img/footer-bg.jpg');

    .container{
        display: flex;
        justify-content: space-between;

        .top-left{
            display: flex;
            justify-content: space-between;

            .col {
                margin-right: 25px;
            }
        }

        .top-right{
            width: 600px;

            img{
                object-fit: cover;
                width: 100%;
                height: 100%;
            }
        }
    }
}

.footer-bottom{
    width: 100%; 
    height: 150px; 
    background-color: $footer-color;

    .container{
        display: flex; 
        justify-content: space-between;
    }
}



</style>