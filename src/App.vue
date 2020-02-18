<template>
  <div id="app">
    <transition name="router-fade" mode="out-in">
      <router-view/>
    </transition>
  </div>
</template>

<style lang="scss">
  @import './common/style/common';
  // #app{
  //   min-width: 980px;
  // }
 .router-fade-enter-active, .router-fade-leave-active {
      transition: opacity .5s;
    }
  .router-fade-enter, .router-fade-leave-active {
    opacity: 0;
  }
</style>
