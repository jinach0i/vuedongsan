<template>
    <div class="gnb-wrap" v-if="openGnb==true">
        <div class="inner">
            <ul>
                <li><a href="#">홈</a></li>
                <li><a href="#">아파트</a></li>
                <li><a href="#">원룸/투룸</a></li>
                <li><a href="#">경매</a></li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'GnbWrap',
    props:{
        openGnb:Boolean,
    },
}
</script>

<style>
    .gnb-wrap{width: 100%; height: 83vh; background-color: #fff; position: absolute; top: 64px; left: 0; right: 0; bottom: 0; z-index: 1; transition: all 2s;}
    .gnb-wrap .inner{margin: 0 auto;}
    .gnb-wrap .inner ul{display: flex; justify-content: space-around; height: 83vh; line-height: 83vh;}
    .gnb-wrap .inner ul li{width: 100%; border-right: 1px solid #ddd; transition: background .8s;}
    .gnb-wrap .inner ul li:hover{background-color: rgb(199, 224, 174);}
    .gnb-wrap .inner ul li:last-child{border-right: none;}
    .gnb-wrap .inner ul li a{font-weight: bold;}
</style>