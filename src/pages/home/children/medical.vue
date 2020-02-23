<template>
    <div class="wapper">
        <ul class="medical">
            <li v-for="(item,index) in list" :key="index">
                <img :src="item.imgUrl" alt="">
                <div class="box">
                    <h4>{{item.name}}</h4>
                    <span>{{item.eName}}</span>
                </div>
            </li>    
        </ul>
    </div>
</template>

<script>
export default {
  name: 'medical',
  data(){
      return {
          list: [
              {imgUrl:require('@/common/img/medical/index226789886.jpg'),name:'健康品',eName:'Health products'},
              {imgUrl:require('@/common/img/medical/index232905902.jpg'),name:'药品',eName:'drug'},
              {imgUrl:require('@/common/img/medical/index244026099.jpg'),name:'医疗器械',eName:'medical devices'},
              {imgUrl:require('@/common/img/medical/index255271869.jpg'),name:'中药资源',eName:'chinese medicine'},
              {imgUrl:require('@/common/img/medical/index265691151.jpg'),name:'茶品',eName:'tea products'}
          ]
      }
  },
  
  created() {
    
  },
  mounted(){
  
  },
  computed: {

  },
  methods:{
 
  }
}
</script>

<style scoped lang="scss">
    @import '@/common/style/mixin';
    .wapper{
        width: 100%; 
        background-image: url('../../../common/img/medical/index21.jpg');
        background-size: cover;
    }
    @media screen and (max-width: 900px){
        .medical{
            width: 100%;
            display: flex;
            flex-wrap: wrap;
            li{
                width: 33.33%;
            }
        } 
    }
    @media screen and (max-width: 1200px){
        .medical{
            width: 100%;
            display: flex;
            flex-wrap: nowrap;
            li{
                width: 20%;
            }
        } 
    }

    @media screen and (min-width: 1200px){
        .medical{
            width: 80%;
            display: flex;
            flex-wrap: nowrap;
            li{
                width: 20%;
            }
        }    
    }
       .medical{
            height: auto;
            margin: 0 auto;
            padding: 80px 0;
            
            li{
                height: auto;
                img{
                    width: 40%;
                    display: block;
                    margin: 0 auto;
                    border-radius: 50%;
                    border: 1px solid rgb(117, 117, 117);
                    transition: 0.5s;
                }
                .box{
                    width: 100%;
                    padding-top: 20px;
                    text-align: center;
                    h4{
                        font-size: 18px;
                    }
                    span{
                        color: rgb(117, 117, 117);
                    }
                }
                &:hover{
                    img{
                        transform: rotateY(180deg);
                        border: 1px solid $red;
                    }
                    h4,span{
                        color: $red;
                    }
                }
            }
        }
</style>