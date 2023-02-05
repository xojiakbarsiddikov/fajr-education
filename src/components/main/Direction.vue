<template>
  <div class="container" id="about">
    <div class="images df justify-center align-center">
      <img :src="require('/src/assets/images/directions.png')" alt="направления">
    </div>
  </div>
</template>

<script>
export default {
  name: "vDirection"
}
</script>

<style scoped>

.images{
  width: 100%;
  margin: 0 0 150px 0;
}

.images img{
  width: 80%;
}

@media (max-width: 500px) {
  .images{
    margin: 250px 0 100px !important;
  }

  .images img{
    width: 90%;
  }

  .container{
    height: unset;
  }
}


</style>