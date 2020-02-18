<template>
    <div class="title">
            <!-- 第一个标题 -->
        <div class="title-1">
            <img class="logo" src="@/common/img/logo.png" alt="仁和" title="仁和">
            <span class="classify iconfont " :class="flag ? 'icon-cha': 'icon-sanheng'" @click=" flag = !flag "></span>
        </div>
        <!-- 第二个标题 -->
        <ul class="title-2" :class="flag ? 'bottom' : ''">
            <li class="bar" v-for="item in list" :key="item.id">
                <h4 class="barName">{{item.name}}</h4>
                <span 
                    v-if="item.children"  
                    class="iconfont icon-ai-arrow-down" 
                    :class="item.flag ? 'trans' : ''"  
                    @click="putDown(item.id)"
                ></span>
                <collapse>
                    <ul class="barChildren"  v-show="item.flag">
                        <li v-for="it in item.children" :key="it.id">
                            <a>{{it.name}}</a>
                        </li>
                    </ul>
                </collapse>
            </li>   
        </ul>
  </div>
</template>

<script>
import collapse from '@/common/js/collapse.js';
export default {
  name: 'titleSmall',
  data(){
      return {
          flag: false,
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
    putDown(id){
        this.list.map(item => {
            if(item.id === id){
                item.flag = !item.flag;
            }
        })
    }
  },
  components:{
      collapse
  }
}
</script>

<style scoped lang="scss">
    @import '@/common/fonts/iconfont';
    @import '@/common/style/mixin';
    @media screen and (max-width: 990px){
   
        .title{
            position: sticky;
            top: 0;
            z-index: 9;
            
        }
        .title-1{
            width: 100%;
            height: 52px;
            position: relative;
            z-index: 9;
            background-color: #fff;
            .logo{
                @include ct;
                left:24px;
                height: 20px;
            }
            .classify{
                @include ct;
                right: 46px;
            }
        }
        .title-2 {
            height: calc(100vh - 52px);
            width: 100%;
            position: absolute;
            bottom: 0;
            z-index: 1;
            display: flex;
            flex-flow: column;
            transition: 0.3s linear;
            background-color: rgba(0,0,0,0.9);
            .bar{
                width: 100%;
                max-height: auto;
                transition: 1s linear;
                position: relative;
                transition: 1s;
                border-bottom: 1px dashed #fff;
                cursor: pointer;
                .barName{
                    line-height: 50px;
                    color: #fff;
                    font-size: 14px;
                    padding-left: 6px;
                    &:hover{
                        color: $red;
                    }
                }
                span{
                    color: #fff;
                    @include ct;
                    right: 8px;
                    top: 18px;
                    transition: 0.2s;
                    transform:rotate(-90deg);
                }
                .barChildren{
                    width: 100%;  
                    height:auto;
                    li{
                        width: 100%;
                        display: list-item;
                        &:nth-of-type(1){
                            border-top: 1px dashed #fff;
                        }
                        a{
                            line-height: 50px;
                            color: #eee;
                            font-size: 12px;
                            padding-left: 12px;  
                            &:hover{
                              color: $red;
                            } 
                        }
                    }
                }

            }
        }
        .trans {
            transform:rotate(0deg) !important;
        }
        .bottom{
            transform: translateY(100%);
        }
    }
    @media screen and (min-width: 990px){
        .title{
            display: none;
        }
      
    }
 
</style>