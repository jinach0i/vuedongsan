<template>
    <div class="black-bg">
        <!-- v-if="모달창열렸니 == true" @click.prevent.self="모달창열렸니 = false;" -->
        <div class="white-bg">
            <!-- <button class="closebtn" @click="모달창열렸니 = false;">X</button> -->
            <img :src="원룸목록[clickedIndex].image" alt="미리보기">
            <h4>{{ 원룸목록[clickedIndex].content }}</h4>
            <p>{{ 원룸목록[clickedIndex].title }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name:'ModalWrap',
    props:{
        모달창열렸니:Boolean,
        clickedIndex:Number,
        원룸목록:Array,
    }
}
</script>

<style>
.black-bg{display: none; position: fixed; top: 0; left: 0; right: 0; bottom: 0; width: 100%; height: 100%; background: rgba(0, 0, 0, .2); padding: 4%;}
.black-bg .white-bg{width: 100%; min-height: 400px; border-radius: 8px; background: white; padding: 20px;}
.black-bg .white-bg .closebtn{float: right; background: transparent; transform: scale(1.5);}
.black-bg .white-bg h4{clear: both; margin-top: 24px;}
</style>