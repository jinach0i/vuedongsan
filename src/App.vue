<template>
  <div id="wrap">
    <header>
      <nav class="navbar ">
        <h1><a class="navbar-brand" href="#"><img alt="Vue logo" src="./assets/logo.png">Vuedongsan</a></h1>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarTogglerDemo02"
          aria-controls="navbarTogglerDemo02" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarTogglerDemo02">
          <ul class="navbar-nav mr-auto">
            <li class="nav-item" v-for="메뉴 in 메뉴들" :key="메뉴">
              <a class="nav-link" href="#">{{ 메뉴 }} <span class="sr-only">(current)</span></a>
            </li>
            <li class="nav-item dropdown">
              <a class="nav-link dropdown-toggle" href="#" role="button" data-toggle="dropdown" aria-expanded="false">
                Dropdown
              </a>
              <div class="dropdown-menu">
                <a class="dropdown-item" href="#" v-for="메뉴 in 메뉴들" :key="메뉴">{{ 메뉴 }}</a>
                <div class="dropdown-divider"></div>
                <a class="dropdown-item" href="#">Something else here</a>
              </div>
            </li>
          </ul>
          <form class="form-inline my-2 my-lg-0">
            <input class="form-control mr-sm-2" type="search" placeholder="Search">
            <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
          </form>
        </div>
      </nav>
    </header>
    <div id="container">
      <div class="card-group">
        <div class="card listing" v-for="(작명, i) in 원룸목록" :key="i">
          <img :src="원룸목록[i].image" class="card-img-top" alt="매물">
          <div class="card-body">
            <h5 class="card-title price">{{ 원룸목록[i].price }}원/월</h5>
            <p class="card-text rooms">방 2개+화장실 1개</p>
            <p class="card-text content">{{원룸목록[i].content}}</p>
            <p class="card-text address" @click="모달창열렸니=!false">{{ 원룸목록[i].title }}</p>
            <p><a href="#">단와부동산</a></p>
            <ul class="remote-controller">
              <li><a href="#">📞</a></li>
              <li><a href="#">🚘</a></li>
              <li><a href="#">✅</a></li>
            </ul>
            <div class="reportbox"><button @click="신고수[0]++">신고</button><span>신고수: {{ 신고수[0] }}</span></div>
            <a href="#" class="btn btn-primary">자세히 보기</a>
          </div>
        </div>
      </div>
      <div class="black-bg" v-if="모달창열렸니==true" @click="모달창열렸니=false">
        <div class="white-bg">
          <button class="closebtn" @click="모달창열렸니=false">X</button>
          <h4>상세페이지 제목</h4>
          <p>내용</p>
        </div>
      </div>
    </div>
    <footer id="footer" :style="스타일도됨">
      <div class="inner">
        <address><a href="index.html">ⓒVuedongsan by 최혜진</a></address>
      </div>
    </footer>
  </div>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import roomlist from "./assets/roomlist";
export default {
  name: 'App',
  data() {
    return {
      원룸목록: roomlist,
      price1: 60,
      스타일도됨: 'background-image:linear-gradient(to left, #f07167,#fed9b7)',
      products: ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
      메뉴들: ['Home', 'For Sale', 'About'],
      신고수: [0,0,0],
      모달창열렸니:false,
    }
  },
  methods: {
    increase(){this.신고수++}
  },
  components: {
    // HelloWorld
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#wrap {
  margin: 0 auto;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
}

li {
  list-style: none;
}

a {
  text-decoration: none !important;
  color: #2c3e50 !important;
}

button {
  border: none;
}

.inner {
  margin: 0 auto;
  max-width: 1130px;
  padding: 0 30px;
}

header {
  padding: 0 1%;
  /* background-image: linear-gradient(-118deg, #ffcfd7, #ffd6bf); */
}

header h1 {}

header h1 a {}

header h1 a img {
  height: 28px;
  margin-right: 6px;
}

header nav {}

header nav ul {}

.listing {
  border-bottom: 1px solid #ddd;
}

#container {}

#container .card {}

#container .card img {}

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

.black-bg{position: fixed; top: 0; left: 0; right: 0; bottom: 0; width: 100%; height: 100%; background: rgba(0, 0, 0, .2); padding: 4%;}
.black-bg .white-bg{width: 100%; min-height: 400px; border-radius: 8px; background: white; padding: 20px;}
.black-bg .white-bg .closebtn{float: right; background: transparent; transform: scale(1.5);}
.black-bg .white-bg h4{clear: both;}
footer {
  width: 100%;
  height: 10vh;
  line-height: 10vh;
  position: fixed;
  bottom: 0;
}

footer address {
  text-align: center;
  font-weight: bold;
}
</style>
