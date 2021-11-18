<template>
  <div id="app">
    <img class="logo" alt="logo" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQHC8IdAgcqkQTLMgldF9_dcXs2fq2Xs64cxcLKc8VLCgJOS1wY3YgSViH4rGfSeyqG0os&usqp=CAU">
    <SelectionForm
      v-bind:pizzaList="pizzaList" 
      v-bind:orders="orders"
    />
  </div>
</template>

<script>
import SelectionForm from './components/SelectionForm.vue'
export default {
  name: 'App',
  data() {
    return {
      pizzaList: [
        {id:1, img:'https://s1.eda.ru/StaticContent/Photos/120131085053/171027192707/p_O.jpg', name:'Paperoni', price:123},
        {id:2, img:'https://hips.hearstapps.com/hmg-prod.s3.amazonaws.com/images/delish-caramel-apple-pizza-still001-1536958428.jpg', name:'Apple', price:342},
        {id:3, img:'https://media.istockphoto.com/photos/vegetarian-pizza-mozzarella-cheese-onions-tomatoes-peppers-zucchini-picture-id685795386', name:'Mozarella', price:560},
        {id:4, img:'https://tmbidigitalassetsazure.blob.core.windows.net/rms3-prod/attachments/37/1200x1200/Wild-Mushroom-Pizza_EXPS_FT19_244460_F_0813_1.jpg', name:'Mushroom', price:760},
        {id:5, img:'https://media.istockphoto.com/photos/pizza-with-pineapple-and-ham-on-white-background-picture-id503580316', name:'Ananas', price:510},
        {id:6, img:'https://tmbidigitalassetsazure.blob.core.windows.net/rms3-prod/attachments/37/1200x1200/Apple-Pizza_exps33461_UH2321897A05_12_5bC_RMS.jpg', name:'Veggie Pizza', price:480},
        {id:7, img:'https://s1.eda.ru/StaticContent/Photos/120131085053/171027192707/p_O.jpg', name:'Hawaiian Pizza.', price:123},
        {id:8, img:'https://hips.hearstapps.com/hmg-prod.s3.amazonaws.com/images/delish-caramel-apple-pizza-still001-1536958428.jpg', name:'Meat Pizza', price:342},
        {id:9, img:'https://media.istockphoto.com/photos/vegetarian-pizza-mozzarella-cheese-onions-tomatoes-peppers-zucchini-picture-id685795386', name:'Buffalo Pizza', price:560},
        {id:10, img:'https://tmbidigitalassetsazure.blob.core.windows.net/rms3-prod/attachments/37/1200x1200/Wild-Mushroom-Pizza_EXPS_FT19_244460_F_0813_1.jpg', name:'BBQ Chicken Pizza', price:760},
        {id:11, img:'https://media.istockphoto.com/photos/pizza-with-pineapple-and-ham-on-white-background-picture-id503580316', name:'Africana', price:510},
        
     ],
      orders: []
    }
  },
  components: {
    SelectionForm
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.logo{
}
</style>
