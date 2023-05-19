<template>


  <Modal :products = 'products' :modalclick = 'modalclick' :openmodal = 'openmodal'/>

  <div class="menu">
    <a v-for='(item,i) in menus' :key="i">{{item}}</a>
  </div>
  
  <!-- 속성은 : -->
  <!-- {{데이터이름}}데이터 집어넣기 위해 -->

  <div @click="openmodal = true, modalclick = i" v-for="(item,i) in products" :key='i'>
    <img :src="item.image" class="room-img">
    <h4>{{item.title}}</h4>
    <p>{{item.price}}만원</p>
    <p>{{item.content}}</p>
  </div>
  
</template>

<script>

import room_data from './assets/oneroom.js';
import Modal from './Modal.vue';

export default {
  name: 'App',
  data(){ //데이터 보관함 object 형식으로
    return {
      modalclick : 0,
      openmodal : false,
      reportCount : [0,0,0],
      prices : [50,60,70],
      products : room_data,
      menus : ['Home','Products','About'],
    }
  },
  components: {
    Modal,
  }
}
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  margin : 0;
}
div {
  box-sizing: border-box;
}

.menu {
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  padding: 30px;
  color: white;
}

.room-img {
  width: 50%;
  margin-top: 40px;
}

.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

</style>
