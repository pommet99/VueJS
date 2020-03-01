<template>
  <v-app id="app">

 <v-carousel hide-delimiters>
<v-carousel-item
  v-for="(item,i) in items"
  :key="i"
  :src="item.src">
</v-carousel-item>
</v-carousel>

<v-row class="text-center">
 <v-col>
  <br>
  <h1>{{ Message | Upper}}</h1>
<br>
  <h2>Join us and explore the world, find below the best destinations to travel to.</h2>
<br>

  </v-col>
</v-row>

<div class="cards">
<v-row>
<destinations class="mt-10" v-for="card in cards" :key="card.id" :image="card.image" :title="card.title" :city="card.city" :country="card.country"></destinations>
</v-row>
</div>

<button class="buy" v-on:click="buy= !buy">Buy Random Ticket</button>
<p v-if="buy">Successfully Bought!</p>
    
<footer>
<img class="img" src="https://image.flaticon.com/icons/svg/776/776541.svg">
</footer>

  </v-app>
</template>

<script>
import destinations from './components/HelloWorld';

export default {
  name: 'App',
  components: {
    destinations
  },
data:function(){
 return {
  items: [
   { src: 'https://images.unsplash.com/photo-1508672019048-805c876b67e2?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1000&q=80'},
   { src: 'https://images.unsplash.com/photo-1503220317375-aaad61436b1b?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1000&q=80'},
   { src: 'https://images.unsplash.com/photo-1476514525535-07fb3b4ae5f1?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1000&q=80'},
   ],
  cards: [
   {image: "https://images.unsplash.com/photo-1550340499-a6c60fc8287c?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1000&q=80", title: "TOP 10 French Destinations", city: "Paris", country: "France"},
   {image: "https://images.unsplash.com/photo-1505761671935-60b3a7427bad?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1050&q=80", title: "TOP 10 British Destinations", city: "London", country: "United-Kingdom"},
   {image: "https://images.unsplash.com/photo-1531572753322-ad063cecc140?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1055&q=80", title: "TOP 10 Italian Destinations", city: "Rome", country: "Italy"},
   {image: "https://images.unsplash.com/photo-1523531294919-4bcd7c65e216?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1050&q=80", title: "TOP 10 Spanish Destinations", city: "Barcelona", country: "Spain"},
   {image: "https://images.unsplash.com/photo-1534430480872-3498386e7856?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1050&q=80", title: "TOP 10 American Destinations", city: "New York", country: "United States of America"},
   {image: "https://images.unsplash.com/photo-1484201349078-7ba3cbc019c1?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1231&q=80", title: "TOP 10 Canadian Destinations", city: "Banff", country: "Canada"},
    ],
  buy:false,
  Message:'Discover !',
  }
},
filters: {
  Upper: function(value) {
    if (!value) return ''
    value = value.toString()
    return value.toUpperCase();
  }
}
};


</script>

<style>
h1{
  color:black;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 40px;
  margin-top:20px;
}

h2{
  color:black;
  font-size:18px;
}

b{
  color:red;
  padding:3px;
  border-radius:25px;
}

b:active{
  background-color: lightpink;
}

footer{
  height: 80px;
  background-color: rgb(36, 35, 35);
  margin-top: 80px;
}

.buy{ 
  width: 150px;
  height: 50px;
  background-color: lightgrey;
  margin-left: 45%;
  margin-top: 70px;
  border-radius:25px;
}

.buy:active{
  background-color: grey;
}

p{
  margin-left: 45%;
  margin-top: 30px;
}

.img{
  margin-top: 15px;
  width:100px;
  height:50px;
  margin-left:46%;
}
</style>