<template>
 <div class="container" id="contact">
   <div class="content df justify-between">
     <div class="form">
       <div class="text text-center">
         <h2>{{ title }}</h2>
       </div>
       <form>
         <h3>Birinchi BEPUL darsimizga yozilish uchun<br>
           raqam:</h3>
         <h4>(91) 490-44-04</h4>
         <h3>Manzil:</h3>
         <h4>Andijon shahri Boburshox ko'chasi 13 </h4>
         <h4>Yangi bozor, IRIS kafe atrofida</h4>
         <h3>Ish vaqti:</h3>
         <h4 class="enter-text">Dush-Shan - 8:00-17:00;
           Yakshanba - dam olish</h4>
         <h3>Contact:</h3>
         <a href="https://t.me/Fajrqabul"><h4>@Fajrqabul</h4></a>
       </form>
     </div>
     <div class="image-content">
       <img :src="require('/src/assets/images/картнка 2 (1).png')" alt="bg">
     </div>
   </div>
   <div class="images-bg">
     <img :src="require('/src/assets/images/Vector (7).png')" alt="vector-bg">
   </div>
 </div>
</template>

<script>
export default {
  name: "vContact",
  data() {
    return {
      title: "Biz bilan aloqa"
    }
  }
}
</script>

<style scoped>
  .form {
    width: 590px;
    height: 498px;
    background: #018FA3;
    box-shadow: 0px 50px 50px -27px rgba(0, 0, 0, 0.1);
    border-radius: 30px;
  }
  form {
    padding: 10px 35px 0;
  }
  .text h2 {
    font-weight: 500;
    font-size: 48px;
    color: #FFFFFF;
    padding: 10px 0 0;
  }
  form h3 {
    font-weight: 600;
    font-size: 24px;
    color: #FFFFFF;
    margin: 15px 0 0;
  }
  form h4 {
    font-weight: 300;
    font-size: 24px;
    color: #FFFFFF;
    margin: 10px 0 0;
  }
  .content {
    align-items: end;
    z-index: 9;
  }
  .image-content img {
    width: 550px;
    height: 653px;
  }
  .images-bg {
    z-index: -9;
    position: absolute;
    top: 0;
    transform: translateY(113px) translateX(45px);
  }
  .container {
    position: relative;
    margin: 50px auto 0;
  }

  @media(max-width: 700px) {
    .content {
      display: block;
    }
    .form{
      width: 430px;
      height: 545px;
      margin: 0 auto;
    }
    .image-content img {
      width: 418px;
      height: 516px;
      text-align: center;
    }
    .image-content {
      margin: 50px 0 0;
    }
    .container {
      margin: 150px auto 0;
    }
    .image-content {
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }

  @media(max-width: 530px) {
    .image-content img {
      width: 410px;
      height: 504px;
      text-align: center;
    }
  }
  @media(max-width: 490px) {
    .form {
      width: 339px;
      height: 436px;
      margin: 0 auto;
    }
    .text h2 {
      font-size: 31px;
    }
    form h3 {
      font-size: 18px;
    }

    form h4 {
      font-weight: 300;
      font-size: 16px;
    }

    .image-content img {
      width: 342px;
      height: 426px;
      text-align: center;
    }
  }
  @media(max-width: 410px) {
    .form {
      width: 339px;
      height: 436px;
      margin: 0 auto;
    }
    .text h2 {
      font-size: 31px;
    }
    form h3 {
      font-size: 18px;
    }

    form h4 {
      font-weight: 300;
      font-size: 16px;
    }

    .image-content img{
      width: 342px;
      height: 426px;
      text-align: center;
    }
  }
  @media(max-width: 390px) {
    .form {
      width: 339px;
      height: 436px;
      margin: 0 auto;
    }
    .text h2 {
      font-size: 31px;
    }
    form h3 {
      font-size: 18px;
    }

    form h4 {
      font-weight: 300;
      font-size: 16px;
    }

    .image-content img {
      width: 342px;
      height: 426px;
      text-align: center;
    }
  }
  @media(max-width: 375px) {
    .form {
      width: 339px;
      height: 436px;
      margin: 0 auto;
    }
    .text h2 {
      font-size: 31px;
    }
    form h3 {
      font-size: 18px;
    }

    form h4 {
      font-weight: 300;
      font-size: 16px;
    }

    .image-content img {
      width: 342px;
      height: 426px;
      text-align: center;
    }
  }

  @media(max-width: 350px) {
    .form {
      width: 330px;
    }
  }
  @media(max-width: 350px) {
    .form {
      width: 297px;
    }
    .image-content img {
      width: 312px;
      height: 391px;
    }
  }
</style>