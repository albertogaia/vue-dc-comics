<template>
        <div class="card">
            <div class="img-card">
                <img :src="prod.thumb" alt="">
            </div>
            <div class="title-card">
                <span>{{prod.series.toUpperCase()}}</span>
            </div>
        </div>
</template>

<script>
export default {
    name: 'ProductCard',
    props: ['prod'],
}
</script>


<style lang="scss" scoped>
@import '@/style/general.scss';

    .card{
        flex-basis: calc(100% / 4 - 30px);
        margin: 15px;

        .img-card{
            aspect-ratio: 1 / 1;
            transition: $fast;
            filter: brightness(0.7);
            cursor: pointer;

            img{
                width: 100%;
                height: 100%;
                object-fit: cover;
                object-position: top;
            }

            &:hover{
                filter: brightness(1.1);
            }
        }

        .title-card{
            color: $txt-light;
            margin-top: 15px;
        }
    }

</style>