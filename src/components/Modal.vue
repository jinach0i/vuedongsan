<template>
    <div class="black-bg" v-if="모달창열렸니==true" @click.self="$emit('closeModal');">
        <div class="white-bg">
            <button class="closebtn" @click="$emit('closeModal')">X</button>
            <div class="modal-container">
                <img :src="원룸목록[clickedIndex].image" alt="미리보기">
                <h4>{{ 원룸목록[clickedIndex].content }}</h4>
                <h4>월 {{ 원룸목록[clickedIndex].price }}원</h4>
                <p>{{ 원룸목록[clickedIndex].title }}</p>
                <input type="text" @input="manyMonth=$event.target.value"><label for="">개월</label>
                <hr>
                <div><strong>총 금액: {{manyMonth*원룸목록[clickedIndex].price}}원</strong></div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'ModalWrap',
    data(){
        return{
            manyMonth:1,
        }
    },
    props:{
        clickedIndex:Number,
        원룸목록:Array,
        모달창열렸니:Boolean,
    },
    
}
</script>

<style>
.black-bg{z-index: 1; position: absolute; top: 0; left: 0; right: 0; bottom: 0; width: 100%; height: 100%; background: rgba(0, 0, 0, .2); padding: 4%;}
.black-bg .white-bg{max-width: 600px; min-height: 400px; border-radius: 8px; background: white; padding: 10px; position: relative; top: 0; left: 0; bottom: 0; margin: 0 auto;}
.black-bg .white-bg .modal-container{padding: 30px}
.black-bg .white-bg .closebtn{float: right; background: transparent; transform: scale(1.5); margin: 5px;}
.black-bg .white-bg h4{clear: both; margin-top: 24px;}
</style>