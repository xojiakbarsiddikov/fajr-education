<template>
 <div class="container">
   <div class="header-images df align-center justify-center">
     <img :src="require('/src/assets/images/Mask Group (1).png')" alt="mask-group">
   </div>
   <div class="content df justify-between">
     <div class="text-wrapper">
       <h1 class="opacity-text">Fajr School</h1>
       <h1 class="text-h1"><span class="text-span">Fajr School</span> - bir bo'lib<br>
         mukammallikka erishamiz</h1>
       <p>{{ description }}</p>
       <button @click="create()">{{ btn }}</button>
     </div>
     <div class="content-bg"></div>
   </div>
   <div class="main-footer df align-center justify-between">
     <img :src="require('/src/assets/images/Mask Group (2).png')" alt="group-2">
     <img :src="require('/src/assets/images/pen_002 1.png')" alt="pen">
     <img :src="require('/src/assets/images/five.png')" alt="five">
   </div>
   <div class="popup-bg" v-if="bg_popup"></div>
   <div class="popups" v-if="modal">
     <div class="popup">
       <form class="form">
         <div class="header-form df justify-between">
           <h2>Ushbu <span class="spans">formani</span> to'ldiring va biz albatta qo'ng'iroq qilamiz!</h2>
           <div class="close" @click.prevent="close()">
             <i class="fa-solid fa-xmark"></i>
           </div>
         </div>
         <input type="text" placeholder="Ismingiz..." v-model="name">
         <input type="number" placeholder="Telefon..." v-model="phone">
         <select class="form-select form-select-lg mb-3" v-model="cors" aria-placeholder="Kurslarimiz...">
           <option value="" disabled selected>Kurslarimiz...</option>
           <option selected v-for="opt in options" :key="opt">{{ opt }}</option>
         </select>
         <textarea placeholder="Izohlar..." v-model="comment"></textarea>
         <button @click.prevent="send()">{{ btn }}</button>
       </form>
     </div>
   </div>
   <div class="modal">
     <div class="content-modal">
       <img :src="require('/src/assets/images/Mask Group.png')" alt="Mask Group">
       <h2><span class="spans">Murojaat</span> uchun rahmat</h2>
       <h2>Tez orada siz <span class="spans">bilan</span> bog'lanamiz</h2>
     </div>
   </div>
 </div>
</template>

<script>
import axios from 'axios'
export default {
  name: "MainMenu",
  data() {
    return {
      name: '',
      phone: '',
      comment: '',
      cors: '',
      modal: false,
      bg_popup: false,
      options: ['Arab tili', 'Tajvid', 'Grammatika'],
      btn: "Ro'yhatdan o'tish",
      description: "Darslarimiz yuqori sifatda, siz istagan ustoz bilan kamida 5 kishi bilan boshlanadi. Quyidagi yo'nalishlarda bepul darslarga ishtirok etishingiz mumkin: arab, rus, ingliz tillari va mental arifmetika! 1-bepul darsimizga yoziling!"
    }
  },
  methods: {
    create() {
      let app = document.querySelector('#app')
      this.modal = true
      this.bg_popup = true

      app.style.overflow = 'hidden'
      app.style.height = 100 + 'vh'
    },
    close() {
      let app = document.querySelector('#app')
      this.modal = false
      this.bg_popup = false

      app.style.overflow = 'auto'
      app.style.height = 'auto'
    },
    send() {
      const TOKEN = '5366282965:AAHyyVJ7VrL7xh8ObyRcR8k24ssJ1FBkIlQ'
      const CHAT_ID = "-1001847240275"
      const URI_API = `https://api.telegram.org/bot${TOKEN}/sendMessage`
      let modal = document.querySelector('.modal')
      let app = document.querySelector('#app')

      let message = `<b>Web saytdan!</b>\n`;
      message += `<b>Ismi: </b> ${ this.name }\n`;
      message += `<b>Telefon raqami: </b> ${ this.phone }\n`;
      message += `<b>Òquv kursi: </b> ${ this.cors }\n`;
      message += `<b>Qo'shimcha Ma'lumoti: </b> ${ this.comment }\n`;

      axios.post(URI_API, {
        chat_id: CHAT_ID,
        parse_mode: 'html',
        text: message,
        date: new Date(Date.now()).toLocaleString()
      })
          .then((res) => {
            console.log(res)
            this.name = ''
            this.phone = ''
            this.cors = ''
            this.comment = ''
            this.modal = false
            setTimeout(() => {
              modal.classList.add('actives')
            }, 200)
            setTimeout(() => {
              modal.classList.remove('actives')
              app.style.overflow = 'auto'
              app.style.height = 'auto'
              this.bg_popup = false
            }, 3000)
          })
          .catch((err) => {
            console.log('htolik yuz berdi', err)
          })
    }
  }
}
</script>

<style scoped>
 .form {
   width: 400px;
   height: 590px;
   background: #F6FAFF;
   border-radius: 30px;
   padding: 25px;
   display: block;
   text-align: center;
 }
 .close {
   cursor: pointer;
 }
 .close i {
   font-size: 22px;
 }
 .form h2 {
   font-weight: 500;
   font-size: 24px;
   text-align: center;
   color: #000000;
   width: 205px;
   margin: 0 auto;
 }
 option[value=""][disabled] {
   display: none;
 }
 .overflow {
   overflow: hidden!important;
   height: 100vh!important;
 }
 .form input, .form select, .form textarea {
   width: 336px;
   height: 60px;
   background: #FFFFFF;
   box-shadow: 0 20px 45px -15px rgba(0, 0, 0, 0.05);
   border-radius: 15px;
   padding: 0 20px;
   color: #000;
   font-size: 19px;
   font-weight: 400;
   margin: 22px 0;
   display: block;
   border: none;
   outline: none;
 }
 .form textarea {
   padding: 18px 20px;
 }
 .form button {
   width: 244px;
   height: 64px;
   background: #FAE01A;
   box-shadow: 0px 20px 40px -27px rgba(0, 0, 0, 0.15);
   border-radius: 30px;
   border: none;
   text-align: center;
   cursor: pointer;
 }
 .form input::placeholder, .form textarea::placeholder {
   font-weight: 300;
   font-size: 18px;
   color: #C2C2C2;
 }
 .opacity-text {
   color: rgba(1, 143, 163, 0.06)!important;
   transform:  translateX(-34px);
 }
 .header-images {
   max-width: 74%;
 }
 .header-images img {
   width: 119.57px;
   height: 120.49px;
 }
 .text-wrapper h1 {
   font-weight: 600;
   font-size: 48px;
   color: #000000;
 }
 .text-span {
   color: #37afe3!important;
 }
 .text-h1 {
   transform: translateY(-38px);
   width: fit-content;
 }
 .content {
   height: 44vh;
 }
 .text-wrapper p {
   width: 532px;
   font-weight: 400;
   font-size: 24px;
   color: #000000;
 }
 .text-wrapper button {
   width: 244px;
   height: 64px;
   background: #FAE01A;
   box-shadow: 0 20px 40px -27px rgba(0, 0, 0, 0.15);
   border-radius: 30px;
   margin: 40px 0 0;
   font-weight: 500;
   font-size: 20px;
   color: #000000;
   cursor: pointer;
 }
 .content-bg {
   background-image: url("../../assets/images/1 картинка (1).png");
   background-position: right top;
   background-repeat: no-repeat;
   width: 640px;
   height: 872px;
   transform: translateY(-182px) translateX(251px);
 }

 .main-footer {
   max-width: 82%;
 }

 .content-modal {
   width: 375px;
   height: 491px;
   background: #F6FAFF;
   border-radius: 30px;
   borden: none;
   text-align: center;
   padding: 94px 0;
 }

 .content-modal h2 {
   font-weight: 500;
   font-size: 33px;
   text-align: center;
   color: #000000;
   line-height: 4vw!important;
   margin-top: 17px;
 }

 .content-modal img {
   width: 120px;
   height: 120px;
   text-align: center;
 }
 .modal-bg{
   background: #ffff;
   opacity: .2;
   width: 100%;
   height: 100vh;
   overflow: hidden;
   position: absolute;
 }

 input[type="number"]::-webkit-outer-spin-button,
 input[type="number"]::-webkit-inner-spin-button {
   -webkit-appearance: none;
 }

 .popup {
   justify-content: end;
   position: absolute;
   top: 0;
   bottom: 0;
   display: flex;
   align-items: center;
   z-index: 2;
   width: 48%;
 }

 .popup-bg {
   position: absolute;
   top: 0;
   bottom: 0;
   display: flex;
   z-index: 2;
   width: 100%;
   background: #000;
   opacity: .5;
   left: 0;
 }

 .modal {
   width: 47%;
   justify-content: end;
   position: absolute;
   top: 0;
   bottom: 0;
   display: flex;
   align-items: center;
   z-index: 2;
   transform: translateY(-994px);
 }

 .actives {
   transition: .6s ease-in-out;
   transform: translateY(0);
 }

 .spans {
   color: #37afe3!important;
 }

 @media(max-width: 1600px) {
   .content-bg {
     width: 688px;
     transform: translateY(-182px) translateX(181px);
     background-position: left top;
   }
   .main-footer {
     max-width: 61%;
     margin: 76px 0 0;
   }
 }

 @media(max-width: 1500px) {
   .content-bg {
     transform: translateY(-182px) translateX(122px);
   }
 }
 @media(max-width: 1400px) {
   .content-bg {
     transform: translateY(-182px) translateX(132px);
     width: 788px;
   }
   .container {
     max-width: 1134px;
   }
   .main-footer {
     max-width: 56%;
   }
 }

 @media(max-width: 1210px) {
   .content-bg {
     transform: translateY(-182px) translateX(84px);
   }
   .main-footer {
     max-width: 56%;
   }
   .container {
     max-width: 478px;
   }
 }

 @media(max-width: 1200px) {
   .content-bg {
     transform: translateY(-182px) translateX(85px);
   }
 }


 @media(max-width: 700px) {
   .text-wrapper button {
     position: relative;
     z-index: 2;
   }
   .content-bg {
     display: none;
   }
   .content-modal {
     height: 311px;
     padding: 59px 0;
     width: 388px;
     margin: 0 auto;
   }
   .container {
     max-width: 407px;
   }
   .content {
     display: block;
   }
   .main-footer {
     margin: 178px 0!important;
     display: block;
   }
   .header-images {
     display: none;
   }
   .content {
     height: 49vh;
     margin: 30px 0 0;
   }
   .text-wrapper p {
     width: 411px;
   }
   .content-modal img {
     width: 80px;
     height: 82px;
   }

   .content-modal h2 {
     font-size: 18px;
     margin-top: 24px;
   }
   .main-footer img {
     width: 145px;
   }

   .popup {
     width: 67%;
   }

   .modal {
     width: 68%;
     justify-content: center;
   }

   .content-modal {
     height: 394px;
     padding: 98px 0;
   }
   .main-footer {
     display: none;
   }
 }

 @media screen and (max-width: 600px), screen and (max-height: 650px) {
   .content {
     height: 73vh;
   }
 }

 @media screen and (max-width: 550px), screen and (max-height: 880px) {
   .content {
     height: 56vh;
   }
 }

 @media(max-width: 590px) {
   .popup {
     width: 68%;
   }
   .modal {
     width: 70%;
     justify-content: center;
   }
 }

 @media(max-width: 580px) {
   .popup {
     width: 70%;
   }
 }

 @media(max-width: 570px) {
   .popup {
     width: 74%;
   }
   .popup {
     width: 72%;
   }
 }

 @media(max-width: 550px) {
   .popup {
     width: 74%;
   }
 }

 @media(max-width: 540px) {
   .popup {
     width: 75%;
   }
   .modal {
     width: 75%;
     justify-content: center;
   }
 }

 @media(max-width: 530px) {
   .text-wrapper h1 {
     font-size: 41px;
   }
   .text-wrapper p {
     font-size: 18px;
     width: 358px;
   }
   .text-wrapper button {
     width: 227px;
     height: 52px;
   }
   .popup {
     width: 77%;
   }
   .modal {
     width: 78%;
     justify-content: center;
   }
 }
 @media(max-width: 530px) {
   .popup {
     width: 77%;
   }
   .content {
     height: 31vh;
     margin: 30px 0 0;
   }
   .modal {
     width: 80%;
     justify-content: center;
   }
   }

 @media(max-width: 510px) {
   .popup {
     width: 80%;
   }
   .modal {
     width: 82%;
   }
 }

 @media(max-width: 490px) {
   .popup {
     width: 86%;
   }
 }

 @media(max-width: 480px) {
   .modal {
     width: 84%;
   }
 }

 @media(max-width: 460px) {
   .content-modal {
     width: 373px;
   }
   .popup {
     width: 87%;
   }
   .modal {
     width: 87%;
     justify-content: center;
   }
   .text-wrapper h1 {
     font-size: 34px;
   }
 }

 @media(max-width: 450px) {
   .content-modal {
     width: 364px;
   }
 }

 @media(max-width: 430px) {
   .content-modal {
     width: 341px;
   }
 }

 @media(max-width: 420px) {
   .content-modal {
     width: 334px;
   }
   .popup {
     width: 90%;
   }
   .modal {
     width: 90%;
     justify-content: center;
   }
   .content {
     height: 24vh;
   }
 }

 @media(max-width: 390px) {
   .content-modal {
     width: 282px;
   }
   .content {
     height: 23vh;
     margin: 30px 0 0;
   }
   .popup {
     width: 87%;
   }
   .form {
     width: 338px;
   }

   .form input {
     width: 284px;
     height: 60px;
   }

   .modal {
     width: 87%;
     justify-content: center;
   }
   .main-footer {
     display: none;
   }
   .text-wrapper h1 {
     font-size: 32px;
   }
   .text-wrapper p {
     font-size: 16px;
     width: 278px;
   }
   .form input, .form select, .form textarea {
     width: 287px;
   }
 }

 @media(max-width: 380px) {
   .content-modal {
     width: 300px;
   }
   .text-wrapper p {
     font-size: 13px;
     width: 278px;
   }
   .opacity-text {
     transform: translateX(-23px);
   }
   .text-wrapper button {
     width: 203px;
     height: 47px;
     font-size: 17px;
   }
 }

 @media(max-width: 375px) {
   .text-wrapper h1 {
     font-size: 32px;
   }
 }

 @media(max-width: 375px) {
   .content {
     height: 33vh;
   }
   .content-modal {
     width: 282px;
   }
   .popup {
     width: 87%;
   }
   .form {
     width: 338px;
   }

   .form input, .form select, .form textarea {
     width: 284px;
     height: 60px;
   }

   .modal {
     width: 87%;
     justify-content: center;
   }
   .main-footer {
     display: none;
   }
 }

 @media(max-width: 340px) {
   .content-modal {
     width: 264px;
   }
 }

 @media(max-width: 350px) {
   .content-modal {
     width: 247px;
   }
   .text-wrapper h1 {
     font-size: 30px;
   }
 }

 @media(max-height: 640px) {
   .content {
     height: 50vh;
   }
 }

 @media(max-height: 480px) {
   .content {
     height: 71vh;
   }
 }

 @media(max-height: 660px) {
   .content {
     height: 46vh;
   }
 }

 @media(max-height: 500px) {
   .content {
     height: 66vh;
   }
 }

 @media screen and (max-width: 375px), screen and (max-height: 670px) {
   .content {
     height: 48vh;
   }
 }

 @media(max-height: 360px) {
   .content {
     height: 73vh;
   }
 }

</style>