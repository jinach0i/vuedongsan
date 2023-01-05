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
    margin: 0; animation: bgTr 2s infinite;
}
.discount-wrapper p{width: 100%; }
@keyframes bgTr {
    from{}
    to{background: orange}
}
.discount-wrapper p{height: 60px; line-height: 60px; font-weight: bold; font-size: 1.4rem; margin: 0 !important;}
</style>