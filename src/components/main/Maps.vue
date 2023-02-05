<template>
  <div class="container df">
    <div class="content df">
      <div class="images">
        <img :src="require('/src/assets/images/Vector (8).png')" alt="vector-bg">
        <img :src="require('/src/assets/images/Vector (9).png')" alt="vector-bg" class="img">
      </div>
      <div class="maps">
        <div class="maps-content">
          <div style="position:relative;overflow:hidden;"><a
              href="https://yandex.uz/maps/org/fajr_school/223545794572/?utm_medium=mapframe&utm_source=maps"
              style="color:#eee;font-size:12px;position:absolute;top:0px;">Fajr school</a><a
              href="https://yandex.uz/maps/10329/andijan/category/foreign_language_courses/184106160/?utm_medium=mapframe&utm_source=maps"
              style="color:#eee;font-size:12px;position:absolute;top:14px;">Andijonda chet tili kurslari</a>
            <iframe
                src="https://yandex.uz/map-widget/v1/?ll=72.357130%2C40.755542&mode=search&oid=223545794572&ol=biz&z=17.78"
                width="860" height="500" frameborder="1" allowfullscreen="true" style="position:relative;" class="mobile"></iframe>
          </div>
        </div>
      </div>
      <div class="img-content">
        <img :src="require('/src/assets/images/Vector (10).png')" alt="vector-bg" class="imagess">
        <img :src="require('/src/assets/images/Vector (11).png')" alt="vector-bg">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "vMaps"
}
</script>

<style scoped>
.images, .img-content {
  position: relative;
  width: fit-content;
}

.img {
  position: absolute;
  right: 0;
  top: 0;
  transform: translateY(15px) translateX(-3px);
}
.maps {
  transform: translateX(-121px);
}
.maps-content {
  width: 794px;
  height: 539px;
  border: 20px solid #000000;
  border-radius: 20px;
}
.imagess {
  position: absolute;
  right: 0;
  top: 0;
  transform: translateY(15px) translateX(-17px);
}
.content {
  align-items: center;
  height: 108vh;
}
.img-content {
  transform: translateX(-245px) translateY(126px);
  z-index: -9;
}

.images {
  transform: translateY(-101px);
}
.container {
  justify-content: end;
}
@media(max-width: 700px) {
  .images, .img-content{
    display: none;
  }
  .maps-content {
    width: 437px;
    height: 520px;
  }
  .mobile {
    width: 401px;
    height: 480px;
  }
  .maps {
    transform: translateY(0);
  }
  .img-content img:nth-child(2) {
    width: 186px;
  }
  .container {
    justify-content: center;
  }
  .imagess {
    transform: translateY(12px) translateX(-16px);
    width: 86%;
  }
}

@media(max-width: 490px) {
  .maps-content {
    width: 393px;
    height: 521px;
  }
  .img-content img:nth-child(2) {
    width: 175px;
  }
  .mobile {
    width: 353px;
  }
}

@media(max-width: 410px) {
  .maps-content {
    width: 361px;
    height: 520px;
  }
  .mobile {
    width: 323px;
  }
}

@media(max-width: 390px) {
  .maps-content {
    width: 337px;
    height: 519px;
  }
  .img-content img:nth-child(2) {
    width: 175px;
  }
  .mobile {
    width: 296px;
  }
}

@media(max-width: 375px) {
  .maps-content {
    width: 317px;
    margin: 0 auto;
  }
  .mobile {
    width: 278px;
  }
  .img-content img:nth-child(2) {
    width: 175px;
  }
}
</style>