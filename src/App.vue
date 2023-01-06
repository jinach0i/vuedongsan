<template>
  <div id="wrap">
    <header>
      <nav>
        <h1><a class="navbar-brand" href="#"><img alt="Vue logo" src="./assets/logo.png">Vuedongsan</a></h1>
        <button class="menubtn" type="button" @click="toggleMenu" ><span></span><span></span><span></span></button>
      </nav>
      <GnbWrap :openGnb="openGnb"/>
    </header>
    <div id="container">
      <BannerDiscount />
      <div class="card-group">
        <ListingCard @openModal="모달창열렸니=true; clickedIndex=$event;" v-for="(a,i) in 원룸목록" :key="i" :원룸목록="원룸목록[i]" :신고수="신고수[i]" />
      </div>
      <ModalWrap @closeModal="모달창열렸니=false" :모달창열렸니="모달창열렸니" :clickedIndex="clickedIndex" :원룸목록="원룸목록"/>
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
import BannerDiscount from './components/Discount.vue';
import ListingCard from './components/Card.vue';
import ModalWrap from './components/Modal.vue';
import GnbWrap from './components/Gnb.vue'
export default {
  name: 'App',
  data() {
    return {
      clickedIndex: 0,
      원룸목록: roomlist,
      price1: 60,
      스타일도됨: 'background-image:linear-gradient(to left, rgb(103 240 183 / 96%), rgb(254, 217, 183))',
      products: ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
      메뉴들: ['Home', 'For Sale', 'About'],
      신고수: [0,0,0,0,0,0],
      모달창열렸니:false,
      오브젝트:{name:'choi',age:30},
      openGnb:false,
    }
  },
  methods: {
    increase(){this.신고수++},
    toggleMenu(){
      const btn=document.querySelector('.menubtn');
      btn.classList.toggle('on');
      this.openGnb=!this.openGnb;

    },
  },
  components: {
    // HelloWorld,
    BannerDiscount,
    ListingCard,
    ModalWrap,
    GnbWrap,
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
  text-decoration: none;
  color: #2c3e50 !important;
}

img{width: 100%;}

button {
  border: none; background: transparent;
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

header h1 {font-size: 1.2rem; margin-bottom: unset;}

header h1 a {}

header h1 a img {
  width: 28px;
  height: 28px;
  margin-right: 6px;
}

header nav {height: 58px; line-height: 58px; display: flex; justify-content: space-between; align-items: center;}

header nav .menubtn {width: 34px; height: 34px; position: relative; }
header nav .on span{transform: rotate(45deg);}
header nav .on span::before{display: none;}
header nav .on span::after{top: 0 !important; transform: rotate(90deg);}

header nav .menubtn span{width: 30px; height: 2px; background-color: black; position: absolute; top: 50%; left: 2px; color: black;}
header nav .menubtn:hover span,header nav .menubtn:hover span::before,header nav .menubtn:hover span::after{background: rgba(183, 230, 95, 0.685); transition: all .4s;}
header nav .menubtn span::before{content: ''; background-color: black; height: 2px; width: 30px; position: absolute; bottom: 10px; left: 0;transition: all .4s;}
header nav .menubtn span::after{content: ''; background-color: black; height: 2px; width: 30px; position: absolute; top: 10px; left: 0;transition: all .4s;}
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
