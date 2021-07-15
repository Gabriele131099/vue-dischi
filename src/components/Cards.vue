
<template>
  <div class="product-card col-3  px-15">
    <div
      class="img-container"
    >
        <img :src="poster" alt="">
    </div>
    <h3>{{ title }}</h3>
    <h4>{{ author }}</h4>
    <h4>{{ genre }}</h4>
  </div>
</template>

<style>
    .product-card
    {
        background-color: rgb(25, 25, 59);
        color: white;
    }
    .img-container img{
        padding: 20px;
        width: 100%;
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


