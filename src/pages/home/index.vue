<template>
  <div class="home">
    <v-title></v-title>
    <v-titleSmall></v-titleSmall>
    <v-banner></v-banner>
    <v-goods></v-goods>

  </div>
</template>

<script>
import title from '@/components/title'
import titleSmall from '@/components/titlesmall'
import banner from '@/components/banner'
import goods from './children/goods'
export default {
  name: 'home',
  components: {
    'v-title' : title,
    'v-titleSmall' : titleSmall,
    'v-banner': banner,
    'v-goods': goods,
  }
}
</script>
<style lang="scss" scoped>
  
    .router-fade-enter-active, .router-fade-leave-active {
      transition: transform 1s;
    }
    .router-fade-enter, .router-fade-leave-active {
      transform: scale(2);
    }
</style>