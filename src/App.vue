<template>

  <div class="menu">
    <a v-for="menu in menus" :key="menu"> {{menu}} </a>
  </div>
  <img alt="Vue logo" src="./assets/logo.png">
  
  <div v-for="[product,price, report], i in products" :key="product">
      <h4>{{product}}</h4>
      <p>{{price}}</p>
      <button @click="increase(i)">허위매물 신고</button> <span>신고 수 : {{report}}</span>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      menus : ['타지리에 관해', '케인인님에 관해', '김성근 감독님에 관해'],
      products : [['뭉탱이', '60만원', 999], ['유링게슝', '100만원', 0], ['아이그냥', '80만원', 0]],
    }
  },

  methods : {
    increase(i){
      this.products[i][2]++;
    }
  },

  components: {
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
  margin-top: 60px;
}

.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color:white;
  padding: 10px;
}
</style>
