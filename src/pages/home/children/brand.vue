<template>
    <div class="wapper">
        <div class="brand">
            <div class="topTitle">
                <span>品牌</span>
            </div>
            <div class="list">
                <li v-for="item in list" :key="item.id" class="animated zoomIn"  >
                    <img :src="item.imgUrl" alt="仁和" title="仁和" />
                </li>
            </div>
            <div class="buttomTitle">
                <span>更多+</span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'brand',
  data(){
      return {
          list: [
              {id:'1', imgUrl:require('@/common/img/pic.png')},
              {id:'2', imgUrl:require('@/common/img/pic.png')},
              {id:'3', imgUrl:require('@/common/img/pic.png')},
              {id:'4', imgUrl:require('@/common/img/pic.png')},
              {id:'5', imgUrl:require('@/common/img/pic.png')},
              {id:'6', imgUrl:require('@/common/img/pic.png')},
              {id:'7', imgUrl:require('@/common/img/pic.png')},
              {id:'8', imgUrl:require('@/common/img/pic.png')}
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
    goBack(){
      this.$router.go(-1)
    },
    goHome(){
      this.$router.push({path:`/home`})
    }
  }
}
</script>

<style scoped lang="scss">
    @import '@/common/style/mixin';
    @media screen and (max-width: 990px){
        .wapper{
            width: 100%;
            .brand{
                margin: 0 auto;
                width: 100%;
                height: auto;
                background: url('../../../common/img/index7.jpg') no-repeat;
                background-size: cover;
                background-attachment: fixed;
                overflow: hidden;
                .list{
                    width: 100%;
                    display: flex;
                    flex-wrap: wrap;
                    li{
                        width: 50%;
                        background-color: #fff;
                        img{
                            width: 100%;
                            display: block;
                            transition: 0.2s;
                            &:hover{
                                transform: scale(1.2);
                            }
                        }
                        &:nth-of-type(1),
                        &:nth-of-type(4),
                        &:nth-of-type(5),
                        &:nth-of-type(8){
                            background-color: #eee;
                        }
                    }
                }
                .topTitle{
                        width: 100%;
                        height: calc(88px - 27px);
                        margin-bottom: 27px;
                        padding-top: 28px;
                        text-align: center;
                        border-bottom: 1px solid rgb(170, 170, 170);
                        span{
                            color: #000;
                            font-weight: 900;
                            font-size: 21px;
                            padding-bottom: 4px;
                            border-bottom: 3px solid #000;
                        }
                }
                .buttomTitle{
                        width: 100%;
                        height: 80px;
                        text-align: center;
                        padding-top: 22px;
                        span{
                            display: block;
                            width: 160px;
                            height: 38px;
                            font-size: 14px;
                            line-height: 38px;
                            margin: auto;
                            position: relative;
                            transition: 0.3s;
                            cursor: pointer;
                            color: rgb(170, 170, 170);
                            box-sizing: border-box;
                            border: 1px solid rgb(170, 170, 170);
                            &::before,
                            &::after{
                                content: '';
                                width: 1000px;
                                @include ct;
                                border-bottom: 1px solid rgb(170, 170, 170);
                            }
                            &::before{
                                right: 105%;
                            }
                            &::after{
                                left: 105%;
                            }
                            &:hover{
                                color: #fff;
                                background-color: $red;
                            }
                        }
                }
            }
        }
    } 
    @media screen and (min-width: 990px){
        .wapper{
            width: 100%;
            .brand{
                margin: 0 auto;
                width: 80%;
                height: auto;
                background: url('../../../common/img/index7.jpg') no-repeat;
                background-size: cover;
                background-attachment: fixed;
                overflow: hidden;
                .list{
                    width: 100%;
                    display: flex;
                    flex-wrap: wrap;
                    li{
                        width: 25%;
                        background-color: #fff;
                        img{
                            width: 100%;
                            display: block;
                            transition: 0.2s;
                            &:hover{
                                transform: scale(1.2);
                            }
                        }
                        &:nth-of-type(1),
                        &:nth-of-type(3),
                        &:nth-of-type(6),
                        &:nth-of-type(8){
                            background-color: #eee;
                        }
                    }
                }
                .topTitle{
                        width: 100%;
                        height: calc(186px - 41px);
                        padding-top: 72px;
                        margin-bottom: 41px;
                        text-align: center;
                        border-bottom: 1px solid rgb(170, 170, 170);
                        span{
                            color: #000;
                            font-weight: 900;
                            font-size: 35px;
                            padding-bottom: 26px;
                            border-bottom: 3px solid #000;
                        }
                }
                .buttomTitle{
                        width: 100%;
                        height: 160px;
                        text-align: center;
                        padding-top: 51px;
                        span{
                            display: block;
                            width: 220px;
                            height: 42px;
                            line-height: 42px;
                            margin: auto;
                            position: relative;
                            transition: 0.3s;
                            cursor: pointer;
                            color: rgb(170, 170, 170);
                            box-sizing: border-box;
                            border: 1px solid rgb(170, 170, 170);
                            &::before,
                            &::after{
                                content: '';
                                width: 1000px;
                                @include ct;
                                border-bottom: 1px solid rgb(170, 170, 170);
                            }
                            &::before{
                                right: 105%;
                            }
                            &::after{
                                left: 105%;
                            }
                            &:hover{
                                color: #fff;
                                background-color: $red;
                            }
                        }
                }
            }
        }
    }
      
</style>