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
      <CardWrap :원룸목록="원룸목록" :신고수="신고수"/>
      <ModalWrap :모달창열렸니="모달창열렸니" :clickedIndex="clickedIndex" :원룸목록="원룸목록"/>
    </div>
    <BannerDiscount />
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
import BannerDiscount from './components/Discount.vue';
import ModalWrap from './components/Modal.vue';
import CardWrap from './components/Card.vue';
export default {
  name: 'App',
  data() {
    return {
      clickedIndex: 0,
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
    increase(){this.신고수++},
  },
  components: {
    // HelloWorld,
    BannerDiscount,
    ModalWrap,
    CardWrap,
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
