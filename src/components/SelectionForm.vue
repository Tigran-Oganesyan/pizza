<template>
  <div class="main">
    <button class="prev" @click="prev">&#8592;</button>
    <div class="wrapper">
      <div class="list" :style="{'margin-left': '-' + (100 * currentIndex) + '%'}">
        <PizzaItem
          v-on:order="orderForm"
          v-for="item of pizzaList" :key="item.id"
          v-bind:item="item"
        />
      </div>
    </div>
    <button class="next" @click="next">&#8594;</button>
      <OrderingForm 
        v-on:toggle="toggle"
        v-bind:show="show" 
        v-bind:OrderingName="OrderingName"  
        v-bind:OrderingPrice="OrderingPrice"
      />
    <div>
    </div>
  </div>
</template>

<script>
import PizzaItem from './PizzaItem.vue'
import OrderingForm from './OrderinfForm.vue'
export default ({
  data() {
    return {
      show:false,
      OrderingName:'',
      OrderingPrice:'',
      currentIndex: 0
    }
  },
  props: ['pizzaList'],
  components: {
    PizzaItem,
    OrderingForm,
  },
  methods: {
    orderForm(name, price){
      this.show = true
      this.OrderingName = name
      this.OrderingPrice = price
    },
    toggle(){
      this.show = false
    },
    next(){
      if(this.currentIndex > this.pizzaList.length - (this.pizzaList.length - 1)){
        this.currentIndex = 0
      } else {
        this.currentIndex++
        console.log(this.currentIndex)
      }
    },
    prev(){
      if(this.currentIndex > 0){
        this.currentIndex--
        console.log(this.currentIndex)
      }
    }
  }
})

</script>

<style scoped>
.main{
  display: flex;
  justify-content: center;
  align-items: center;
}
.wrapper{
  max-width: 750px;
  max-height: 525px;
  overflow: hidden;
}
.list{
  box-sizing: border-box;
  display: flex;
  justify-content: flex-start;
  flex-wrap: wrap;
}
button{
  width: 50px;
  height: 20px;
}
</style>


