<template>
    <div class="order" v-if="show">
      <button class="exit" v-on:click="$emit('toggle')">x</button>
      <img alt="logo" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQHC8IdAgcqkQTLMgldF9_dcXs2fq2Xs64cxcLKc8VLCgJOS1wY3YgSViH4rGfSeyqG0os&usqp=CAU">
      <h3 class="makeOrder">Make order</h3>
			<div class="orderNamePrice">
        <h3>{{OrderingName}}</h3>
				<h3>{{OrderingPrice}}</h3>
			</div>
      <div class="address">
      <p>Address</p>
      <form class="form" @submit.prevent="Submit">
        <input type="text" v-model="street" placeholder="street">
        <input type="text" v-model="house" placeholder="house">
        <input type="text" v-model="flat" placeholder="flat">
        <button type="submit">make order</button>
      </form>
    </div>
    </div>
</template>

<script>
export default {
	props: ['show', 'OrderingName', 'OrderingPrice'],
  data() {
    return {
      street:'',
      house:'',
      flat:'',
    }
  },
  methods: {
    Submit(){
      console.log(this.OrderingName,this.street,this.house,this.flat);
      this.street ='',
      this.house = '',
      this.flat = ''
    }
  }
}

</script>

<style scoped>
	.order{
		border: 1px solid black;
    position: fixed;
    top: 25%;
    bottom: 0;
    right: 0;
    left: 25%;
    background-color: white;
    box-shadow: 1px 1px 5px 5px;
    height: 400px;
    width:500px;
    z-index: 1050;
	}
  .makeOrder{
    text-align: center;
  }
  .orderNamePrice{
    width: 25%;
    margin-left: 25px;
    display: flex;
    justify-content: space-between;
  }
  .address{
    display: flex;
    justify-content: center;
    align-items:baseline;
  }
  .form{
    display: flex;
    flex-direction: column;
    margin-left: 20px;
  }
  .exit{
    position: absolute;
    right: 0;
    border: none;
    font-size: 45px;
    color: red;
    background-color: white;
  }

</style>