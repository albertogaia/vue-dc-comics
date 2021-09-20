<template>
    <div class="my-content">
        <div class="container">
            <div class="products">
                <h2>Content goes here</h2>
            </div>
            
        </div>
    </div>
</template>

<script>
export default {
    name: 'Products',
}
</script>

<style scoped lang="scss">
@import '@/style/general.scss';

.my-content{
    background-color: $secondary-color;
    height: 150px;
}

h2{color: $txt-light;}
.container{height: 100%;}
.products{
    height: 100%;
    @include centerCol(vertical);
}

</style>