<template>
    <div class="wapper">
        <div class="show">
            <div class="showLeft left">
                <h3>大客户产品展示</h3>
                <div class="showBox">
                    <img src="" alt="">
                    <div class="title">
                        <h3>药都仁和是仁和药业吗</h3>
                        <span>08-07</span>
                        <p>药都仁和，是属于仁和企业下面的一个子商标。很多人把仁和企业说成仁和药业。仁和企业下面子公司十多个。目前只有仁和药业上市，名气大。打个比方。仁和企业（仁和药业）是爹，那药都仁和、仁和匠心等等子公司、子商标就是儿子。这些儿子里面有生产产品的、也</p>
                        <a href="">Read more ----></a>
                    </div>
                </div>
            </div>
            <div class="showRight right">
            <h3>健康小课堂</h3>
            <div class="news">
                <h4>药都仁和赤小豆芡实薏仁茶有什么功效？</h4>
                <span>11-28</span>
                <p>已经是累到很久了现在才想到给自己身体调理调理，网上看看觉得这个人参黄精黑枸杞茶还是不错的哎，先买一袋，试着喝一段时间再说效果哈。总是要对自己好一点</p>
            </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'show',
    data(){
        return {

        }
    },
    computed:{

    },
    watch:{
       
    },
    mounted() {
     
    },
    methods:{
    }
}
</script>
<style lang="scss" scoped>
    @import '@/common/style/mixin';
    @import '@/common/fonts/iconfont';
    .wapper{
        width: 100%;
        .show{
            width: 1310px;
        }
    }

    @media screen and (max-width: 990px){
        .showLeft{
            width: 640px;
            height: auto;
            h3{
                margin-top: 83px;
                margin-bottom: 37px;
                line-height: 63px;
                font-weight: 700;
                position: relative;
                &::before{
                    content: '';
                    width: 70px;
                    height: 1px;
                    border-bottom: 2px;
                    position: absolute;
                    bottom: 0;
                    left: 0;
                }
            }
            .showBox{
                width: 100%;
                height: auto;
                img{
                    display: block;
                    width: 100%;
                }
                .title{
                    width: 100%;
                    height: 300px;
                    overflow: hidden;
                }
            }
        }
    }
    

   
</style>