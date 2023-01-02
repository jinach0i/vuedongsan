<template>
  <div class="card listing">
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
      <a href="#" class="btn btn-primary">자세히 보기</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ListingCard',
  props: {
    원룸목록: Object,
    신고수: Array,
  }
}
</script>

<style>
.listing {
  border-bottom: 1px solid #ddd;
}

#container .card .remote-controller {
  display: flex;
  justify-content: center;
  width: 100%;
  align-items: center;
  padding: 0;
}

#container .card .remote-controller li {
  width: 13.3333%;
  margin-right: 5%;
}

#container .card .remote-controller li a {
  display: inline-block;
}

#container .card .remote-controller li:nth-child(1) a {
  transform: translate(5px, 1.5px);
  font-size: 17px;
}

#container .card .remote-controller li:nth-child(2) a {
  transform: translateY(-1px);
  font-size: 19px;
}

#container .card .remote-controller li:nth-child(3) {
  margin-right: 0;
}

#container .card .remote-controller li:nth-child(3) a {
  transform: translateY(1px);
}
</style>