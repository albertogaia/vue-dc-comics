<template>
  <header>
      <div class="header-top"></div>
      <div class="header-nav container">
        <div class="logo">
          <a href="/"><img src="@/assets/img/dc-logo.png" alt="logo.png"></a>
        </div>
        <div class="nav-menu">
          <ul class="nav-items">
            <li v-for="(link, index) in links" :key="index" class="nav-item" :class="(link.current) ? 'active' : null">
              <a :href="link.url">{{link.text.toUpperCase()}}</a>
            </li>
          </ul>
        </div>
      </div>
  </header>
</template>

<script>
import Links from '@/assets/data/Links.js'
export default {
  name: 'Header',
  data(){
    return{
      links: Links.headerLinks,
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/general";

.header-top{height: 60px; width: 100%; background-color: $secondary-color;}
.header-nav{height: 100px; display: flex; justify-content: space-between; align-items: center; border-bottom: 4px solid transparent}

.logo {
  width: 70px;
  padding: 20px 0px;
  img{width: 100%;}
}
.nav-menu{height: 100%;}
.nav-items{list-style: none; display: flex; font-size: 12px; font-weight: 600; line-height: 100px;}
.nav-item{
  padding: 0px 15px;
  color: $secondary-color;
  a{
    text-decoration: none;
    color: inherit;

    &:hover{
      color: $primary-color;
    }

  }

  &.active{
      color: $primary-color;
      border-bottom: 4px solid $primary-color;
  }

}



</style>
