<template>
    <div class="container-socials">
        <div v-for="(social, index) in socialsLink" :key="index" class="img-social">
            <a :href="social.url"><img :src="require(`../assets/${social.icon}`)" :alt="social.name"></a>
        </div>
    </div>
</template>

<script>
import {socials} from '@/assets/data/Socials.js'
export default {
    name: 'SocialsIcons',

    data(){
        return {
            socialsLink: socials,
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/general';
    .container-socials{
        display: flex;

        .img-social{
            width: 30px;
            margin-left: 20px;
            transition: $fast;

            img{
                width: 100%;
            }

            &:hover{
                filter: brightness(1.3);
            }
        }

    }
</style>