<template>
  <div class="home">
    <v-title></v-title>
    <v-titleSmall></v-titleSmall>
    <v-banner></v-banner>
    <v-brand></v-brand>
    <v-goods></v-goods>
    <v-show></v-show>
    <div class="box"></div>
  </div>
</template>

<script>
import title from '@/components/title'
import titleSmall from '@/components/titlesmall'
import banner from '@/components/banner'
import goods from '@/components/goods'
import brand from './children/brand'
import show from './children/show'
export default {
  name: 'home',
  components: {
    'v-title' : title,
    'v-titleSmall' : titleSmall,
    'v-banner': banner,
    'v-brand': brand,
    'v-goods' : goods,
    'v-show' : show,
  }
}
</script>
<style lang="scss" scoped>
  .box{
    width: 100%;
    height: 100px;
  }
    .home{
      background-color: #fff;
    }
    .router-fade-enter-active, .router-fade-leave-active {
      transition: transform 1s;
    }
    .router-fade-enter, .router-fade-leave-active {
      transform: scale(2);
    }
</style>