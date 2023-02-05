<template>
 <div class="container">
    <div class="top-content df justify-between">
      <div class="text-wrapper">
        <img :src="require('/src/assets/images/круг.png')" alt="круг">
        <div class="text">
          <h4>{{ description }}</h4>
        </div>
      </div>
      <div class="img-wrapper">
        <img :src="require('/src/assets/images/teachers.png')" alt="teacher">
      </div>
    </div>
   <div class="bottom-content df justify-between align-center">
     <div class="img-wrapper">
       <img :src="require('/src/assets/images/students.png')" alt="student">
     </div>
     <div class="text-wrapper wrap-text">
       <div class="text transform">
         <h4>{{ description2 }}</h4>
       </div>
       <div class="catalog-images">
         <img :src="require('/src/assets/images/круг 2.png')" alt="круг2">
       </div>
     </div>
   </div>
 </div>
</template>

<script>
export default {
  name: "vProduct",
  data() {
    return {
      description: "Bizning markazimizda bolalarni sevadigan va o'z ishiga sodiq bo'lgan professional o'qituvchilar ishlaydi. Biz bolalarga intellektual qobiliyatlarini yaxshilashga yordam beramiz ular dunyoni o'rganishlari va uni yanada chiroyli va mehribon qilishlari uchun. ",
      description2: "Hozirgacha 100 dan ortiq o'quvchilar prezident maktabiga imtixon topshirdilar va ularning 13 dan ortig'i prezident maktabi o'quvchisi bo'lishga muvaffaq bo'lishdi"
    }
  }
}
</script>

<style scoped>
  .text-wrapper img {
    width: 201px;
    height: 200px;
  }
  .text h4 {
    width: 459px;
    font-weight: 400;
    font-size: 24px;
    color: #000000;
    transform: translateX(-56px);
    margin: 23px 0;
  }
  .text {
    width: 440px;
    height: 204px;
    background: #FFF7BE;
    border-radius: 30px;
    transform: translateY(53px) translateX(-58px);
  }
  .text-wrapper {
    align-items: start;
  }
  .img-wrapper img {
    width: 590px;
    height: 440px;
  }
  .transform {
    transform: translateX(126px)!important;
  }
  .top-content, .bottom-content {
    align-items: start;
  }
  .text-wrapper  {
    height: 31vh;
    display: flex;
    align-items: center;
  }
  .top-content {
    height: 53vh;
  }
  .wrap-text img {
    width: 201px;
    margin: 67px 0;
    height: 205px;
  }

  .wrap-text {
    display: flex;
    height: 42vh!important;
    align-items: center;
  }
  .catalog-images {
    transform: translateY(70px);
    z-index: -2;
  }
  
  @media(max-width: 700px) {
    .top-content, .bottom-content {
      display: block;
    }

    .text {
      width: 300px;
      height: 180px;
      transform: translateY(53px) translateX(-111px);
    }
    .text-wrapper img {
      width: 150px;
      height: 150px;
      margin: 0 auto;
    }

    .text h4 {
      width: 333px;
      font-size: 18px;
      margin: 28px 0;
      transform: translateX(-38px);
    }

    .img-wrapper {
      margin: 85px 0;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .img-wrapper img {
      width: 433px;
      height: 300px;
    }

    .top-content {
      height: 83vh;
    }
    .wrap-text {
      height: 17vh!important;
    }
  }

  @media(max-width: 530px) {
    .text {
      transform: translateY(53px) translateX(-83px);
    }
  }
  @media(max-width: 510px) {
    .text {
      transform: translateY(53px) translateX(-73px);
    }
  }

  @media(max-width: 500px) {
    .text {
      transform: translateY(53px) translateX(-68px);
    }
    .top-content {
      height: 71vh;
    }
  }
  @media(max-width: 490px) {
    .text {
      transform: translateY(53px) translateX(-54px);
    }
    .transform {
      transform: translateX(72px)!important;
    }
    .text-wrapper img {
      height: 94px;
      width: 90px;
    }
    .text h4 {
      width: 321px;
      font-size: 16px;
    }
  }
  @media(max-width: 450px) {
    .img-wrapper img {
      width: 375px;
      height: 280px;
    }
  }
  @media(max-width: 414px) {
    .text {
      transform: translateY(53px) translateX(-30px);
    }
    .img-wrapper img {
      width: 367px;
      height: 277px;
    }
    .text-wrapper img {
      height: 104px;
      width: 90px;
    }
    .catalog-images {
      transform: translateY(79px);
    }
  }
  @media screen and (max-height: 414px) and (max-height: 896px) {
    .top-content {
      height: 69vh!important;
    }
  }
  @media(max-width: 410px) {
    .img-wrapper img{
      width: 388px;
      height: 300px;
    }

  }
  @media(max-width: 390px) {
    .text {
      width: 266px;
      height: 180px;
      transform: translateY(53px) translateX(-41px);
    }
    .text h4 {
      width: 305px;
      font-size: 15px;
    }
    .transform {
      transform: translateX(58px)!important;
    }
    .text-wrapper img {
      height: 83px;
      width: 74px;
    }
    .img-wrapper img {
      width: 347px;
      height: 269px;
    }
    .top-content {
      height: 69vh;
    }
  }
  @media(max-width: 375px) {
    .text {
      width: 266px;
      height: 180px;
      transform: translateY(53px) translateX(-33px);
    }
    .text {
      transform: translateY(53px) translateX(-33px);
    }
    .text h4 {
      width: 305px;
      font-size: 15px;
    }
    .transform {
      transform: translateX(58px)!important;
    }
    .text-wrapper img {
      width: 76px;
      height: 81px;
    }
  }
  @media screen and (max-width: 375px) and (max-height: 667px) {
    header {
      height: 167vh;
    }
    .top-content {
      height: 79vh;
    }
  }

  @media(max-width: 350px) {
    .img-wrapper img {
      width: 309px;
      height: 241px;
    }
    .text {
      transform: translateY(53px) translateX(-21px);
    }
    .text-wrapper img{
      width: 76px;
      height: 83px;
    }
    .text h4 {
      width: 285px;
      font-size: 13px;
    }
  }

  @media(max-width: 350px) {
    .text {
      width: 251px;
      height: 165px;
    }
    .img-wrapper img {
      width: 309px;
      height: 210px;
    }
    .text-wrapper img {
      width: 67px;
      height: 74px;
    }
  }

  @media(max-height: 360px) {
    .top-content {
      height: 120vh!important;
    }
  }
</style>