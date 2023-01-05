<template>
    <div class="black-bg" v-if="모달창열렸니==true" @click="emitClose">
        <div class="white-bg">
            <button class="closebtn" @click="$emit('closeModal')">X</button>
            <div class="modal-container">
                <img :src="원룸목록[clickedIndex].image" alt="미리보기">
                <h4>{{ 원룸목록[clickedIndex].content }}</h4>
                <p>{{ 원룸목록[clickedIndex].title }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'ModalWrap',
    props:{
        clickedIndex:Number,
        원룸목록:Array,
        모달창열렸니:Boolean,
    },
    methods:{
        emitClose(){this.$emit('closeModal',this.원룸목록.id)},
    },
}
</script>

<style>
.black-bg{position: fixed; top: 0; left: 0; right: 0; bottom: 0; width: 100%; height: 100%; background: rgba(0, 0, 0, .2); padding: 4%;}
.black-bg .white-bg{width: 100%; min-height: 400px; border-radius: 8px; background: white; padding: 10px;}
.black-bg .white-bg .modal-container{padding: 20px}
.black-bg .white-bg .closebtn{float: right; background: transparent; transform: scale(1.5); margin: 5px;}
.black-bg .white-bg h4{clear: both; margin-top: 24px;}
</style>