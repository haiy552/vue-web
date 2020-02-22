<template>
    <div class="wapper">
        <h3 class="subject">产品</h3>
        <el-carousel class="goodsList" ref="goodsList" :interval="5000" arrow="never" trigger="clcik"  indicator-position="outside" :height="height">
            <el-carousel-item class="list" v-for="(item, index) in num" :key="index">
               <div class="page" ref="page" v-for="it in changList[index]" :key="it.id" >
                   <div class="img">
                       <div class="bg"></div>
                       <img  :src="it.imgUrl" alt="" @load="setHeight">
                   </div>
                    <div class="title">
                        <h3>{{it.name}}</h3>
                        <h4>{{it.context}}</h4>
                    </div>
                </div>
            </el-carousel-item>
        </el-carousel>
    </div>
</template>

<script>

export default {
    name: 'goods',
    data(){
        return {
            step: 8,
            height:'',
            list: [
                {id:'1', imgUrl:require('@/common/img/血压计列表图2638515.jpg'), name:'仁和血压计', context:'仁和血压测量仪 【功能】心律测量测量脉博测量血压高血'},
                {id:'2', imgUrl:require('@/common/img/大麦若叶.jpg'), name:'仁和大麦若叶青汁', context:'青汁'},
                {id:'3', imgUrl:require('@/common/img/血压计列表图2638515.jpg'), name:'仁和血压计', context:'仁和血压测量仪 【功能】心律测量测量脉博测量血压高血'},
                {id:'4', imgUrl:require('@/common/img/大麦若叶.jpg'), name:'仁和大麦若叶青汁', context:'青汁'},
                {id:'5', imgUrl:require('@/common/img/血压计列表图2638515.jpg'), name:'仁和血压计', context:'仁和血压测量仪 【功能】心律测量测量脉博测量血压高血'},
                {id:'6', imgUrl:require('@/common/img/大麦若叶.jpg'), name:'仁和大麦若叶青汁', context:'青汁'},
                {id:'7', imgUrl:require('@/common/img/血压计列表图2638515.jpg'), name:'仁和血压计', context:'仁和血压测量仪 【功能】心律测量测量脉博测量血压高血'},
                {id:'8', imgUrl:require('@/common/img/大麦若叶.jpg'), name:'仁和大麦若叶青汁', context:'青汁'},
                {id:'9', imgUrl:require('@/common/img/血压计列表图2638515.jpg'), name:'仁和血压计', context:'仁和血压测量仪 【功能】心律测量测量脉博测量血压高血'},
                {id:'10', imgUrl:require('@/common/img/大麦若叶.jpg'), name:'仁和大麦若叶青汁', context:'青汁'},
                {id:'11', imgUrl:require('@/common/img/血压计列表图2638515.jpg'), name:'仁和血压计', context:'仁和血压测量仪 【功能】心律测量测量脉博测量血压高血'},
                {id:'12', imgUrl:require('@/common/img/大麦若叶.jpg'), name:'仁和大麦若叶青汁', context:'青汁'},
                {id:'13', imgUrl:require('@/common/img/血压计列表图2638515.jpg'), name:'仁和血压计', context:'仁和血压测量仪 【功能】心律测量测量脉博测量血压高血'},
                {id:'14', imgUrl:require('@/common/img/大麦若叶.jpg'), name:'仁和大麦若叶青汁', context:'青汁'},
                {id:'15', imgUrl:require('@/common/img/血压计列表图2638515.jpg'), name:'仁和血压计', context:'仁和血压测量仪 【功能】心律测量测量脉博测量血压高血'},
                {id:'16', imgUrl:require('@/common/img/大麦若叶.jpg'), name:'仁和大麦若叶青汁', context:'青汁'}
            ]
        }
    },
    computed:{
        num(){
            return this.list.length/this.step
        },
        changList(){
            let arr = [];
            let start, end;
            for(let i = 0; i < this.num; i++){
                [start, end] = [i*this.step, (i+1)*this.step];
                arr.push(this.list.slice(start, end))
            }
            return arr;
        }
    },
    watch:{
       
    },
    mounted() {
        window.addEventListener('resize', () => {
            this.setHeight()
        })
    },
    methods:{
        setHeight(){
            let widthNum, heightNum;                                                                //横向数量，竖向数量
            let page = this.$refs.page[0];                          
            let [pageW, pageH] = [page.offsetWidth, page.offsetHeight];                             //每个装有图片的宽高
            let htmlWidth = document.scrollingElement.scrollWidth;                                  //html的宽度
            let boxWidth = document.getElementsByClassName('goodsList')[0].offsetWidth;             //goodsList的宽度
            [widthNum, heightNum] = htmlWidth > 990 ?  [4, this.step / 4] : [2, this.step / 2];     
            let jianxi = (boxWidth - (pageW * widthNum)) / (widthNum - 1 );                         //盒子与盒子的间隙                                                                 
            this.height =  (pageH * heightNum + jianxi * (heightNum - 1)) + 'px'                    // 计算出一排有几个盒子的总高度
        }
    }
}

</script>
<style lang="scss" scoped>
    @import '@/common/style/mixin';
    @import '@/common/fonts/iconfont';
    .wapper{
        width: 100%;
        text-align: center;
    }
    .page{
        &:hover{
            .img{
                .bg{
                    background-color: rgba(0,0,0,0.3) !important;
                    &::before{
                        content: '';
                        opacity: 1 !important;
                        left: 50% !important;
                        top: 50% !important;
                        transform: translate(-50%, -50%) rotate(360deg)!important; 
                    }
                    
                }
            }
            .title{
                background-color: $red !important;
            }
            h3,h4{
                color: #fff !important;
            }
        }
    }
    @media screen and (max-width: 990px){
        .goodsList{
            width: 90%;
            margin: 0 auto;
            .list{
                width: 100%;
                display: flex;
                flex-wrap: wrap;
                align-content: space-between;
                justify-content: space-between;
                .page{
                    width: 48%;
                    height: auto;
                    transition: 1s;
                    .img{
                        padding: 20px 40px;
                        height: auto;
                        position: relative;
                        transition: 1s;
                        .bg{
                            width: 100%;
                            height: 100%;
                            @include center;
                            position: absolute;
                        }
                        img{
                            width: 100%;
                            display: block;
                        }
                    }
                    .title{
                        height: 80px;
                        background-color: #eee;
                        text-align: center;
                        padding: 20px 15px;
                        h3,h4{ 
                        overflow: hidden;
                        text-overflow:ellipsis;
                        white-space: nowrap;
                       }
                       h4{
                           color: #8b8b8b;
                       }
                    }

                }

            }
        }
    }
    @media screen and (max-width: 1200px){
        .page{
            .img{
               padding: 10px 30px !important; 
            }
        }
    }
    @media screen and (min-width: 990px){
        .subject{
            font-size: 35px;
            font-weight: 700;
            display: inline-block;
            width: auto;
            border-bottom: 4px solid #000;
            line-height: 80px;
            text-align: center;
            margin-bottom: 30px;
            position: relative;
            &::before{
                content: '';
                bottom: -4px;
                @include cl;
                height: 1px;
                width: 1000px;
                border-bottom: 1px solid #eee;
            }
            
        }
        .goodsList{
            width: 80%;
            margin: 0 auto;
            padding-bottom: 60px;
            border-bottom: 1px dotted rgba(0,0,0,0.8);
            .list{
                width: 100%;
                display: flex;
                flex-wrap: wrap;
                align-content: space-between;
                justify-content: space-between;
                .page{
                    width: 23.5%;
                    height: auto;
                    .img{
                        padding: 20px 40px;
                        height: auto;
                        position: relative;
                        transition: 1s;
                        .bg{
                            width: 100%;
                            height: 100%;
                            @include center;
                            &::before{
                                content:'想要';
                                @include center;
                                text-align: center;
                                line-height: 50px;
                                color: $red;
                                opacity: 0;
                                width: 50px;
                                height: 50px;
                                border-radius: 50%;
                                background-color: #fff;
                                left: 0;
                                transition: 0.5s;
                            }
                        }                        
                        img{
                            width: 100%;
                            display: block;
                        }
                    }
                    .title{
                        width: 100%;
                        height: 80px;
                        background-color: #eee;
                        text-align: center;
                        padding: 20px 30px;
                        h3,h4{ 
                        overflow: hidden;
                        text-overflow:ellipsis;
                        white-space: nowrap;
                       }
                       h4{
                           color: #8b8b8b;
                       }
                    }
                }

            }
        }
    }
    

   
</style>