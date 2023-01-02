<template>
    <div class="discount-wrapper">
        <p>지금 결제하면 20% 할인</p>
    </div>
</template>

<script>
export default {
    name: 'BannerDiscount',
}
</script>

<style>
.discount-wrapper {
    background: lightgreen;
    height: 60px;
    line-height: 60px;
    margin-top: 20px;
    transition: background 1s;
}
</style>