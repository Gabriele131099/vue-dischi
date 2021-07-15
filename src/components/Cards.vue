
<template>
  <div class="product-card">
    <div
      class="img-container"
    >
        <img :src="poster" alt="">
    </div>
    <h3>{{ title }}</h3>
    <div>{{ author }}</div>
    <div>{{ genre }}</div>
  </div>
</template>

<style>
    .product-card
    {
        background-color: rgb(25, 25, 59);
        color: white;
        text-align: center;
        width: calc((100% / 5) - 20px);
        margin: 10px;
    }
    .product-card>div
    {
        color: rgb(63, 61, 61);
    }
    .img-container img{
        padding: 10px;
        width: 100%;
        height: 230px;
    }
</style>

<script>
export default {
  name: 'Cards',
  props: {
    poster: String,
    author: String,
    title: String,
    genre: String,
  },
};
</script>


