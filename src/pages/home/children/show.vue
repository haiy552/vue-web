<template>
    <div class="wapper">
        <div class="show">
            <div class="showLeft left">
                <h3 class="topNavLitle">大客户产品展示</h3>
                <div class="showBox">
                    <img src="@/common/img/pic (1).png" alt="">
                    <div class="bottomNavLitle">
                        <div class="title">
                            <a class="left">药都仁和是仁和药业吗</a>
                            <span class="right">08-07</span>
                        </div>
                        <p>药都仁和，是属于仁和企业下面的一个子商标。很多人把仁和企业说成仁和药业。仁和企业下面子公司十多个。目前只有仁和药业上市，名气大。打个比方。仁和企业（仁和药业）是爹，那药都仁和、仁和匠心等等子公司、子商标就是儿子。这些儿子里面有生产产品的、也...</p>
                        <a class="more" href="#">Read more ----></a>
                    </div>
                </div>
            </div>
            <div class="showRight right">
                <h3 class="topNavLitle">健康小课堂</h3>
                <ul class="news" ref="news">
                    <li class="list" v-for="(item,index) in list" :key="index">
                        <a class="nav">{{item.nav}}</a>
                        <span class="time">{{item.time}}</span>
                        <p>{{item.context}}</p>
                    </li>
                </ul>
            </div>
        </div>
        <!-- <div class="button"><span @click="next">换一组</span></div> -->
    </div>
</template>

<script>

export default {
    name: 'show',
    data(){
        return {
            list: [
                {nav: '药都仁和枇杷秋梨膏有什么效果？', time: '11-28', context: '特别喜欢它们家的药都仁和枇杷秋梨膏！强烈推荐枇杷膏啊！在三亚咳嗽了就心心念念想着这家枇杷膏，吃了以后真的又清凉又止咳，甜度也刚刚好！枇杷膏绝了！'},
                {nav: '药都仁和赤小豆芡实薏仁茶有什么功效？', time: '11-28', context: '已经是累到很久了现在才想到给自己身体调理调理，网上看看觉得这个人参黄精黑枸杞茶还是不错的哎，先买一袋，试着喝一段时间再说效果哈。总是要对自己好一点'},
                {nav: '舒芯宝是什么？', time: '11-28', context: '舒芯宝，它是一款由21味名贵中草药制成的护理贴，跟护垫使用方法很像。舒芯宝，它不是药，却能清除阴道及宫内毒素垃圾，能有效的预防和修复阴道炎、宫颈糜烂、子宫下垂、盆腔炎、附件炎、白带异常、下身异味、真菌感染等慢性妇科疾病。'},
                {nav: '药都仁和枇杷秋梨膏有什么效果？', time: '11-28', context: '特别喜欢它们家的药都仁和枇杷秋梨膏！强烈推荐枇杷膏啊！在三亚咳嗽了就心心念念想着这家枇杷膏，吃了以后真的又清凉又止咳，甜度也刚刚好！枇杷膏绝了！'},
                {nav: '药都仁和赤小豆芡实薏仁茶有什么功效？', time: '11-28', context: '已经是累到很久了现在才想到给自己身体调理调理，网上看看觉得这个人参黄精黑枸杞茶还是不错的哎，先买一袋，试着喝一段时间再说效果哈。总是要对自己好一点'},
                {nav: '舒芯宝是什么？', time: '11-28', context: '舒芯宝，它是一款由21味名贵中草药制成的护理贴，跟护垫使用方法很像。舒芯宝，它不是药，却能清除阴道及宫内毒素垃圾，能有效的预防和修复阴道炎、宫颈糜烂、子宫下垂、盆腔炎、附件炎、白带异常、下身异味、真菌感染等慢性妇科疾病。'}
            ]
        }
    },
    computed:{

    },
    watch:{
       
    },
    mounted() {
     
    },
    methods:{
        next(){
            
        }
    }
}
</script>
<style lang="scss" scoped>
    @import '@/common/style/mixin';
    @import '@/common/fonts/iconfont';
    .wapper{
        width: 100%;
        padding-bottom: 34px;
        background-image: url('../../../common/img/index20.jpg');

        .show{
            width: 1310px;
            padding-top: 60px;
            margin: 0 auto;
            overflow: hidden;
        }
    }
    .left{
        float: left;
    }
    .right{
        float: right;
    }
    @media screen and (max-width: 990px){
        .wapper{
            display: none;
        }
    }
    @media screen and (min-width: 990px){
        .topNavLitle{
            font-size:36px;
            line-height: 94px;
            font-weight: 700;
            text-align: left;
            border-bottom: 1px solid #eee;
            margin-bottom: 40px;
            position: relative;
            &::before{
                content: '';
                width: 70px;
                height: 1px;
                border-bottom: 2px solid #000;
                position: absolute;
                bottom: 0;
                left: 0;
            }
        }
        .showLeft{
            width: 640px;
            height: 760px;
            overflow: hidden;
            .showBox{
                width: 100%;
                height: auto;
                img{
                    display: block;
                    width: 100%;
                }
                .bottomNavLitle{
                    width: 100%;
                    padding: 35px;
                    padding-bottom: 0;
                    background-color: #fff;
                }
                .title{
                    overflow: hidden;
                    position: relative;
                    padding-bottom: 20px; 
                    a{
                        font-size:20px;
                        line-height: 50px;  
                    }
                    span{
                        color: #eee;
                    }
                    &::before{
                            content: '';
                            width: 70px;
                            height: 1px;
                            border-bottom: 3px solid $red;
                            position: absolute;
                            bottom: 0;
                            left: 0;
                        }
                }
                p{
                    padding-top: 22px;
                }
                .more{
                    font-size:17px;
                    line-height: 92px;
                    color: $red;
                }
            }
        }
        .showRight{
            width: 630px;
            height: auto;
            .news{
                width: 100%;
                height: 632px;
                overflow: auto;
                .list{
                    width: 100%;
                    height: 200px;
                    padding: 36px;
                    margin-top:12px;
                    background-color: #fff;
                    &:nth-of-type(1){
                        margin-top:0px;
                    }
                    .nav{
                        font-size:20px;
                        color: #000;
                        
                    }
                    .time{
                        display: block;
                        line-height: 54px;
                        color: #eee;
                    }
                    p{
                        display: -webkit-box;
                        -webkit-box-orient: vertical;
                        -webkit-line-clamp: 2;
                        overflow: hidden;
                    }
                }
            }
        }
        .button{
            height: 100px;
            text-align: center;
            span{
                line-height: 100px;
                border: 1px solid #333;
                padding:5px;
                border-radius: 15px;
                cursor: pointer;
            }
        }
    }
    

   
</style>