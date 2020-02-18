<template>
    <div class="title">
        <div class="context">
            <!-- 第一个标题 -->
            <div class="title-1">
                <img class="logo" src="@/common/img/logo.png" alt="仁和" title="仁和">
                <div class="search">
                    <input type="text">
                    <span class="iconfont icon-fangdajing"></span><!-- 搜索图标 -->
                </div>
                <div class="shop">
                    <h4>商城平台</h4>
                    <span class="iconfont icon-ai-arrow-down"></span><!-- 向下箭头 -->
                </div>
            </div>

            <!-- 第二个标题 -->
            <ul class="title-2">
                <li class="bar" v-for="item in list" :key="item.id">
                    <h4 class="barName">{{item.name}}</h4>
                    <div class="barChildren" v-if="item.children">
                        <img class="xiaojj" src="@/common/img/top5.png" alt="">
                        <li v-for="it in item.children" :key="it.id">
                            <span class="iconfont icon-xingxing1"></span>
                            <h4>{{it.name}}</h4>
                        </li>
                    </div>
                </li>   
            </ul>
        </div>
  </div>
</template>

<script>
export default {
  name: 'titleBig',
  data(){
      return {
          list: [
              {id:'1', name: '首页'},
              {id:'2', name: '品牌产品', flag: false, children: [
                  {id:'2-1', name:'仁和'},
                  {id:'2-2', name:'闪亮'},
                  {id:'2-3', name:'闪亮1'}
              ]},
              {id:'3', name: '团队介绍'},
              {id:'4', name: '高端定制'},
              {id:'5', name: '仁和新零售'},
              {id:'6', name: '健康小课堂', flag: false, children: [
                  {id:'6-1', name:'健康咨询'},
                  {id:'6-2', name:'小新闻'}
              ]},
              {id:'7', name: '关于我们'}
          ]
      }
  },
  
  created() {
    
  },
  computed: {
      
  },
  methods:{

  }
}
</script>

<style scoped lang="scss">
    @import '@/common/fonts/iconfont';
    @import '@/common/style/mixin';
    @media screen and (max-width: 990px){
        .title{
            display: none;
        }
    }
    @media screen and (max-width: 1200px){
        .search input{
            display: none;
        }
    }
    @media screen and (min-width: 990px) {
        .title{
            width:  100%;
            height: 150px;
            position: sticky;
            top: 0;
            z-index: 9;
            background-color: #fff;
        }
        .context{
            width: 80%;
            height: 100%; 
            margin: 0 auto;
        }
        .title-1{
            height: 100px;
            position: relative;
            .logo{
                   height: 58px;
                   @include ct;
               }
            .search{
                position: absolute;
                @include ct;
                height: 30px;
                width: 240px;
                right: 120px;
                input{
                    width: 100%;
                    height: 100%;
                    outline:none;
                    padding-left: 20px;
                    border: 1px solid #eee;
                    border-radius: 15px;
                }
                span{
                    @include ct;
                    right: 8px;
                    color: $red;
                    font-weight: 700;
                }
           }
           .shop{
                @include ct;
                width: 100px;
                height: 30px;
                right: 0;
                display: flex;
                align-items: center;
                justify-content:space-between;
            }
            
        }
        .title-2{
            width: 100%;
            height: 50px;
            display: flex;
            align-items: center;
            background-color: #f8f8f8;
            box-shadow: 0px 8px 7px -1px rgba(0, 0, 0, 0.3);
            .bar{
                flex: 1;
                height: 100%;
                text-align: center;
                position: relative;
                .barName{
                    line-height: 50px;
                    display: block;
                    width: 100%;
                    height: 100%;
                }
                span{
                    display: none;
                }
                .barChildren{
                    top: 60px;
                    width: 100px;
                    border-radius: 5px;
                    opacity: 0;
                    display: flex;
                    flex-flow: column;
                    transition: 0.2s;
                    @include cl;
                    background-color: $red;
                    z-index: 9;
                    .xiaojj{
                        top: -10px;
                        height: 10px;
                        @include cl;
                    }
                    li{
                        position: relative;
                        span{
                            @include ct;
                            z-index: 9999;
                            left: 2px;
                            display: none;
                            transition: 0.2s;
                            color: rgb(210, 238, 49);
                        }
                        h4{
                            padding: 12px 0 12px 0;
                            color: #fff;
                        }
                        &:hover  span{
                            display: block;
                        }
                    }
                }
                &:hover .barName,
                &:hover .barChildren{
                    color: $red;
                    opacity: 1;
                    top: 50px;
                }
                
            }
        }

    }
</style>