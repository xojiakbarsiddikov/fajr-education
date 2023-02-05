<template>
  <div class="content" id="certificate">
    <div class="container text-wrapper text-center">
      <h1>{{ title }}</h1>
    </div>
    <div class="vector-bg df justify-between">
      <div class="images_one">
        <img :src="require('/src/assets/images/Vector (3).png')" alt="vector-bg">
        <img :src="require('/src/assets/images/Vector (5).png')" alt="vector-bg">
        <img :src="require('/src/assets/images/Ellipse 15.png')" alt="Ellipse">
      </div>
      <div class="images_two">
        <img :src="require('/src/assets/images/Vector (4).png')" alt="vector-bg">
      </div>
    </div>
    <div class="container certificate df align-center justify-between descktops">
      <div class="images" v-for="image in images" :key="image.id">
        <img :src="require(`/src/assets/images/${image.img}`)" :alt="image.title">
      </div>
    </div>
    <swiper class="mySwiper mobiles">
      <swiper-slide v-for="image in images" :key="image.id">
        <div class="container certificate df align-center justify-between">
          <div class="images">
            <img :src="require(`/src/assets/images/${image.img}`)" :alt="image.title">
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
import {Swiper, SwiperSlide} from "swiper/vue";
import 'swiper/css';

export default {
  name: "vCertificate",
  data() {
    return {
      title: "Sertifikatlarimiz",
      images: [
        {
          id: 1,
          img: "sertificate1.png",
          title: "sertificate1"
        },
        {
          id: 2,
          img: "sertificate2.png",
          title: "sertificate2"
        },
        {
          id: 3,
          img: "sertificate3.png",
          title: "sertificate3"
        },
        {
          id: 4,
          img: "sertificate4.png",
          title: "sertificate4"
        }
      ]
    }
  },
  components: {
    Swiper,
    SwiperSlide,
  },
}
</script>

<style scoped>
.images_one {
  position: relative;
  transform: translateY(51px);
}

.images_one img:nth-child(2) {
  position: absolute;
  left: 0;
  right: 0;
  transform: translateY(15px);
}

.images_one img:nth-child(3) {
  transform: translateY(-41px) translateX(39px);
  position: absolute;
  left: 0;
  bottom: 0;
}

.descktops {
  display: flex;
}

.mobiles {
  display: none;
}

.vector-bg {
  align-items: end;
}

.certificate {
  transform: translateY(-246px);
}

.content {
  padding: 70px 0 0;
}

.images_two {
  min-width: 17%;
}

.text-wrapper h1 {
  font-weight: 600;
  font-size: 48px;
  color: #000000;
}

@media (max-width: 700px) {
  .vector-bg {
    display: none;
  }

  .swiper-cube-shadow{
    width: 0!important;
    height: 0!important;
  }

  .certificate {
    transform: translateY(0);
    margin: 40px 0 0;
    display: block;
  }

  .text-wrapper h1 {
    font-size: 41px;
  }

  .images {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .images img {
    margin: 20px 0;
  }

  .descktops {
    display: none;
  }

  .mobiles {
    display: block;
    width: 472px;
  }
}

@media (max-width: 490px) {
  .text-wrapper h1 {
    font-size: 31px;
  }

  .mobiles {
    width: 331px;
  }
}

@media (max-width: 390px) {
  .mobiles {
    display: block;
    width: 340px;
  }

  .text-wrapper h1 {
    font-size: 31px;
  }
}

@media (max-width: 375px) {
  .text-wrapper h1 {
    font-size: 31px;
  }

  .mobiles {
    width: 331px;
  }
}

@media (max-width: 350px) {
  .mobiles {
    width: 310px;
  }
}
</style>