<template>
 <div class="container" id="comments">
  <div class="text-wrapper text-center">
    <h1>{{ title }}</h1>
  </div>
   <div class="slider">
     <swiper :navigation="true" :modules="modules" class="mySwiper desctopes">
       <swiper-slide class="swiper-slide df align-center justify-between">
         <div class="slider-content" v-for="comment in comments" :key="comment.id">
           <div class="content">
             <div class="content-header df align-center">
               <img :src="require(`/src/assets/images/${comment.img}`)" :alt="comment.name">
               <h2>{{ comment.name }}</h2>
             </div>
             <div class="text">
               <p>{{ comment.description }}</p>
             </div>
           </div>
         </div>
       </swiper-slide>
       <swiper-slide class="swiper-slide df align-center">
         <div class="slider-content" v-for="comment in products" :key="comment.id">
           <div class="content">
             <div class="content-header df align-center">
               <img :src="require(`/src/assets/images/${comment.img}`)" :alt="comment.name">
               <h2>{{ comment.name }}</h2>
             </div>
             <div class="text">
               <p>{{ comment.description }}</p>
             </div>
           </div>
         </div>
       </swiper-slide>
     </swiper>
     <swiper :navigation="true" :modules="modules" class="mySwiper mobiles">
       <swiper-slide class="swiper-slide df align-center justify-between" v-for="comment in mobile_catalog" :key="comment.id">
         <div class="slider-content">
           <div class="content">
             <div class="content-header df align-center">
               <img :src="require(`/src/assets/images/${comment.img}`)" :alt="comment.name">
               <h2>{{ comment.name }}</h2>
             </div>
             <div class="text">
               <p>{{ comment.description }}</p>
             </div>
           </div>
         </div>
       </swiper-slide>
     </swiper>
   </div>
 </div>
</template>

<script>
import {Swiper, SwiperSlide} from "swiper/vue";
import {Navigation} from "swiper";
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import 'swiper/css/scrollbar';
export default {
  name: "vComments",
  data() {
    return {
      title: "Mijozlarimiz fikrlari",
      comments: [
        {
          id: 1,
          img: "users1.png",
          name: "Malika Fayzieva",
          description: "Men qizimni arab tili kursiga o'qish uchun bergandim 3 oyga qolmay arab tili kitoblarini va sherlarini o'qishni boshladi! Zo'r ustozlar bor"
        },
        {
          id: 2,
          img: "users2.png",
          name: "Oygul Lepessova",
          description: "Zo'r ustozlar bor ekan, ishlarizga omad"
        },
        {
          id: 3,
          img: "users3.png",
          name: "Gulbaxor Meliboyeva",
          description: "Ingliz tili ustozi TOP"
        }
      ],
      products: [
        {
          id: 1,
          img: "users1.png",
          name: "Malika Fayzieva",
          description: "Men qizimni arab tili kursiga o'qish uchun bergandim 3 oyga qolmay arab tili kitoblarini va sherlarini o'qishni boshladi! Zo'r ustozlar bor"
        },
        {
          id: 2,
          img: "users2.png",
          name: "Oygul Lepessova",
          description: "Zo'r ustozlar bor ekan, ishlarizga omad"
        },
        {
          id: 3,
          img: "users3.png",
          name: "Gulbaxor Meliboyeva",
          description: "Ingliz tili ustozi TOP, Men qizimni arab tili kursiga o'qish uchun bergandim 3 oyga qolmay arab tili kitoblarini va sherlarini o'qishni boshladi!"
        }
      ],
      mobile_catalog: [
        {
          id: 1,
          img: "users1.png",
          name: "Malika Fayzieva",
          description: "Men qizimni arab tili kursiga o'qish uchun bergandim 3 oyga qolmay arab tili kitoblarini va sherlarini o'qishni boshladi! Zo'r ustozlar bor"
        },
        {
          id: 2,
          img: "users2.png",
          name: "Oygul Lepessova",
          description: "Zo'r ustozlar bor ekan, ishlarizga omad"
        },
        {
          id: 3,
          img: "users3.png",
          name: "Gulbaxor Meliboyeva",
          description: "Ingliz tili ustozi TOP, Men qizimni arab tili kursiga o'qish uchun bergandim 3 oyga qolmay arab tili kitoblarini va sherlarini o'qishni boshladi!"
        },
        {
          id: 4,
          img: "users4.png",
          name: "Анара Баймаганбетова",
          description: "Zo'r ustozlar bor ekan, ishlarizga omad"
        },
        {
          id: 5,
          img: "users5.png",
          name: "Gulzhan Kossantayeva",
          description: "Men qizimni arab tili kursiga o'qish uchun bergandim 3 oyga qolmay arab tili kitoblarini va sherlarini o'qishni boshladi! Zo'r ustozlar bor"
        },
        {
          id: 6,
          img: "users6.png",
          name: "Енлик Серик ",
          description: "Ingliz tili ustozi TOP, Men qizimni arab tili kursiga o'qish uchun bergandim 3 oyga qolmay arab tili kitoblarini va sherlarini o'qishni boshladi! "

        }
      ]
    }
  },
  setup() {
    return {
      modules: [Navigation],
    };
  },
  components: {
    Swiper,
    SwiperSlide,
  },
}
</script>

<style scoped>
  .text-wrapper h1 {
    font-weight: 600;
    font-size: 48px;
    color: #000000;
  }
  .desctopes{
    display: block;
  }
  .mobiles {
    display: none;
  }
  .content {
    width: 387px;
    height: 284px;
    border: 4px solid #018FA3;
    border-radius: 30px;
    padding: 25px;
    margin: 0 52px 0 15px;
  }
  .text p {
    font-weight: 400;
    font-size: 20px;
    color: #000000;
    width: 327px;
    margin: 10px 0 0;
  }
  .content-header h2 {
    font-weight: 600;
    font-size: 24px;
    color: #000000;
    margin: 0 20px 0;
  }
  .content-header img {
    border-radius: 50px;
  }
  .swiper-slide{
    justify-content: end;
  }
  .text-wrapper {
    height: 13vh;
  }

  @media(max-width: 1210px) {
    .container {
      max-width: 478px;
    }
  }

  @media(max-width: 700px) {
    .desctopes{
      display: none;
    }
    .mobiles {
      display: block;
    }
    .swiper-slide {
      justify-content: center;
    }
    .content {
      margin: 0!important;
    }
  }
  @media(max-width: 490px) {
    .text-wrapper h1 {
      font-size: 32px;
    }
    .content {
      width: 347px;
    }
  }
  @media(max-width: 450px) {
    .content {
      width: 327px;
    }
    .text p {
      font-size: 17px;
      width: 281px;
    }
    .content-header h2 {
      font-size: 20px;
    }
  }
  @media(max-width: 390px) {
    .text-wrapper h1 {
      font-size: 32px;
    }
    .content {
      width: 347px;
    }
  }
  @media(max-width: 375px) {
    .text-wrapper h1 {
      font-size: 32px;
    }
    .content {
      width: 330px;
    }
    .content-header h2 {
      font-size: 20px;
    }
    .text p {
      font-size: 16px;
      width: 269px;
    }
  }

  @media(max-width: 350px) {
    .content {
      width: 328px;
    }
    .content-header h2 {
      font-size: 19px;
    }
    .text p {
      font-size: 14px;
      width: 265px;
      margin: 45px 0 0;
    }
  }
  @media(max-width: 350px) {
    .content {
      width: 306px;
    }
    .content-header h2 {
      font-size: 18px;
    }
    .text p {
      font-size: 12px;
      width: 220px;
    }
  }
</style>