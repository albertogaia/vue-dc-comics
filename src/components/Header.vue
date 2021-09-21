<template>
  <header>
      <div class="header-top">
        <div class="container">
          <SocialsIcons />
        </div>
        
      </div>
      <div class="header-nav container">
        <div class="logo">
          <a href="/"><img src="@/assets/img/dc-logo.png" alt="logo.png"></a>
        </div>
        <div class="nav-menu">
          <ul class="nav-items">
            <li v-for="(link, index) in links" :key="index" class="nav-item" :class="(link == currentLink) ? 'active' : null" @click="currentNav(index)">
              <a :href="link.url">{{link.text.toUpperCase()}}</a>
            </li>
          </ul>
        </div>
      </div>
  </header>
</template>

<script>
import Links from '@/assets/data/Links.js'
import SocialsIcons from '@/components/SocialsIcons.vue'
export default {
  name: 'Header',
  components:{
      SocialsIcons,
  },
  data(){
    return{
      links: Links.headerLinks,
      currentLink: '',
    }
  },
  methods: {
    currentNav(i){
      let tmpLink = this.links[i];
      this.currentLink = tmpLink;
    }
  },
  mounted(){
    this.currentLink = this.links[1];
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "@/style/general";

.header-top{
  height: 60px; 
  width: 100%; 
  background-color: $secondary-color;

  .container{
     @include center(vertical); 
     justify-content: flex-end;
  }
}
.header-nav{height: 100px; @include center(vertical); justify-content: space-between;}

.logo {
  width: 70px;
  padding: 20px 0px;
  transition: $medium;

  &:hover{
    transform: rotate(380deg) scale(1.1);

  }

  img{
    width: 100%;
    }

}
.nav-items{list-style: none; display: flex; font-size: $fs-xs ; font-weight: $bold; line-height: 96px;}
.nav-item{
  padding: 0px 15px;
  color: $secondary-color;
  cursor: pointer;
  transition: $fast;
  border-bottom: 4px solid transparent;
  a{
    text-decoration: none;
    color: inherit;

    &:hover{
      color: $primary-color;
    }

  }

  &:hover{
    color: $txt-blue;
    border-bottom: 4px solid $primary-color;
  }

  &.active{
      color: $primary-color;
      border-bottom: 4px solid $primary-color;
  }

}



</style>
