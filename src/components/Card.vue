<template>
    <div class="card-group">
        <div class="card listing" v-for="(a, i) in 원룸목록" :key="i">
            <img :src="a.image" class="card-img-top" alt="매물">
            <div class="card-body">
                <h5 class="card-title price">{{ a.price }}원/월</h5>
                <p class="card-text rooms">방 2개+화장실 1개</p>
                <p class="card-text content" >{{ a.content }}</p>
                <p class="card-text address">{{ a.title }}</p>
                <p><a href="#">단와부동산</a></p>
                <ul class="remote-controller">
                    <li><a href="#">📞</a></li>
                    <li><a href="#">🚘</a></li>
                    <li><a href="#">✅</a></li>
                </ul>
                <div class="reportbox"><button>신고</button><span>신고수: {{ 신고수[0] }}</span></div>
                <a href="#" class="btn btn-primary" >자세히 보기</a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'CardWrap',
}
</script>

<style>
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