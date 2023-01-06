<template>
  <div class="card listing" @click="emitOpen">
    <img :src="원룸목록.image" class="card-img-top" alt="매물">
    <div class="card-body">
      <h5 class="card-title price">{{ 원룸목록.price }}원/월</h5>
      <p class="card-text rooms">방 2개+화장실 1개</p>
      <p class="card-text content">{{ 원룸목록.content }}</p>
      <p class="card-text address">{{ 원룸목록.title }}</p>
      <p><a href="#">단와부동산</a></p>
      <ul class="remote-controller">
        <li><a href="#">📞</a></li>
        <li><a href="#">🚘</a></li>
        <li><a href="#">✅</a></li>
      </ul>
      <div class="reportbox"><button>신고</button><span>신고수: {{ 신고수 }}</span></div>
      <a href="#" class="btn btn-primary" @click="$emit('openModal')">자세히 보기</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ListingCard',
  props: {
    원룸목록: Object,
    신고수: Number,
  },
  methods:{
    emitOpen(){this.$emit('openModal',this.원룸목록.id)},
    },
}
</script>

<style>
.listing {
  border-bottom: 1px solid #ddd;
}
.card a{text-decoration: none;}
.card p{word-break: keep-all;}
.card .card-body{display: flex; flex-direction: column; justify-content: space-between;}
.card .remote-controller {
  display: flex;
  justify-content: center;
  width: 100%;
  align-items: center;
  padding: 0;
}

.card .remote-controller li {
  width: 13.3333%;
  margin-right: 5%;
}

.card .remote-controller li a {
  display: inline-block;
}

.card .remote-controller li:nth-child(1) a {
  transform: translate(5px, 1.5px);
  font-size: 17px;
}

.card .remote-controller li:nth-child(2) a {
  transform: translateY(-1px);
  font-size: 19px;
}

.card .remote-controller li:nth-child(3) {
  margin-right: 0;
}

.card .remote-controller li:nth-child(3) a {
  transform: translateY(1px);
}
</style>