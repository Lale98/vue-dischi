<template>
  <div class="card">
      <img :src="item.poster" :alt="item.title">
      <h2> {{item.title}} </h2>
      <p> {{item.author}} </p>
      <p> {{item.year}} </p>
  </div>
</template>

<script>
export default {
    props: ['item'],
}
</script>

<style lang="scss" scoped>
    @import '../style/variables';

    .card {
        height: 370px;
        text-align: center;
        display: flex;
        flex-direction: column;
        align-items: center;
        width: calc((100% / 5) - 30px);
        margin: 10px 15px;
        background-color: $mainColor;
        padding: 15px;

        img {
            margin: 15px 0;
            width: 160px;
            height: 160px;
            
        }

        h2 {
            text-transform: uppercase;
            margin: 10px 0; 
            color: white
        }

        p {
            font-size: 18px;
            color: rgba(white, 0.4);
        }
    }
</style>