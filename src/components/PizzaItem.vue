<template>
  <div>
    <div class="item" v-on:click="$emit('order', item.name, item.price)">
      <img class="img" :src="item.img">
      <h2>{{item.name}}</h2>
      <p>Price:{{item.price}} rub</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
  .item{
    border: 1px solid black;
    box-sizing: border-box;
    width: 249px;
    height: 250px;
    margin-bottom: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .img{
    
    width: 150px;
    height: 100px;
  }

</style>