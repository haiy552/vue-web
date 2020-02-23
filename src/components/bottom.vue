<template>
  <div class="wapper">
    <ul class="bottom">
       <li></li> 
    </ul>
  </div>
</template>

<script>
export default {
  name: 'banner',
  data(){
      return {
        height:'',
        list: [
            {name:'快速导航', children: {list: ['首页','品牌产品','团队介绍', '高端定制', '仁和新零售', '健康小课题']}},
            {name:'仁和品牌', children: {list: ['仁和','妇炎洁','药都仁和', '闪亮', '仁和匠心', '仁和药业', '一见倾心', '安亲宝贝']}},
            {name:'联系我们', children: {list: ['0791-83902606', '客服中心']}},
            {name:'关注公众号', url: (require('@/common/img/banner2.jpg'))}
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
    
  }
}
</script>

<style scoped lang="scss">
  
    

</style>