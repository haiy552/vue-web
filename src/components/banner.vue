<template>
  <div class="wapper">
    <el-carousel class="banner" :interval="3000" arrow="never" trigger="clcik" :height="height">
        <el-carousel-item class="list" v-for="item in list" :key="item.id">
          <img ref="img" :src="item.url" alt="" @load="setHeight">
        </el-carousel-item>
    </el-carousel>
  </div>
</template>

<script>
export default {
  name: 'banner',
  data(){
      return {
        height:'',
        list: [
            {id:'1', url: (require('@/common/img/banner1.jpg'))},
            {id:'2', url: (require('@/common/img/banner2.jpg'))},
            {id:'3', url: (require('@/common/img/banner1.jpg'))},
            {id:'4', url: (require('@/common/img/banner2.jpg'))}
        ]
      }
  },
  mounted() {
    window.addEventListener('resize', () => {
      this.setHeight()
    })
  },
  watch:{
  
  },
  methods:{
    setHeight(){
      let img = this.$refs.img[0];
      let [imgW, imgH] = [img.width, img.height];
      let width = document.getElementsByClassName('banner')[0].offsetWidth;
      this.height =  width * (imgH / imgW) + 'px';
    }
  }
}
</script>

<style scoped lang="scss">
    @media screen and (max-width: 990px){
        .wapper{
            width: 100%;
            position: relative;
            z-index: 1;
            .banner{
                margin: 0 auto; 
                width: 100%;
                .list{
                    width: 100%;
                    img{
                        width: 100%;
                        
                    }
                }
                
            }
        }
    }
    @media screen and (min-width: 990px){
        .wapper{
            width: 100%;
            position: relative;
            z-index: 1;
            .banner{
                margin: 0 auto; 
                width: 80%;
                .list{
                    width: 100%;
                    
                    img{
                        width: 100%;
                        
                    }
                }
                
            }
        }
    }

</style>