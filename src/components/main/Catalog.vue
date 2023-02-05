<template>
  <div class="section">
    <div class="container" id="catalog">
      <div class="content">
        <h1 class="text-center">{{ title }}</h1>
        <div class="vector-bg df align-center justify-between">
          <img :src="require('/src/assets/images/Vector.png')" alt="vector-background" class="transform">
          <img :src="require('/src/assets/images/Vector (1).png')" alt="vector-background" class="vector">
        </div>
        <div class="slider">
          <swiper :navigation="true" :modules="modules" class="mySwiper desktops">
            <swiper-slide class="swiper-slide df align-center justify-between">
              <div class="slider-content" v-for="catalog in catalogs" :key="catalog.id">
                <div class="text-wrapper text-center" :class="catalog.class">
                  <h2>{{ catalog.title }}</h2>
                </div>
                <div class="texts">
                  <div class="main-text text-center">
                    <h1>{{ catalog.price }}</h1>
                    <h4 :class="catalog.margin">{{ catalog.year }}</h4>
                    <h4>{{ catalog.watch }}</h4>
                  </div>
                  <div class="menu-wrapper text-center">
                    <ul class="text-center menu">
                      <li>{{ catalog.write }}</li>
                      <li>{{ catalog.list }}</li>
                      <li>{{ catalog.item }}</li>
                      <li>{{ catalog.name }}</li>
                      <li class="active">{{ catalog.text }}</li>
                      <li class="demo" style="display: none">{{ catalog.demo }}</li>
                      <li class="num" style="display: none">{{ catalog.num }}</li>
                      <li class="material" style="display: none">{{ catalog.material }}</li>
                      <li class="texnologic" style="display: none">{{ catalog.texnologic }}</li>
                      <li class="logic" style="display: none">{{ catalog.logic }}</li>
                      <li class="free" style="display: none">{{ catalog.free }}</li>
                    </ul>
                    <button class="catalog-btn text-center" :class="catalog.class" @click="create()">{{ catalog.btn }}</button>
                  </div>
                </div>
              </div>
            </swiper-slide>
            <swiper-slide class="swiper-slide df align-center justify-between">
              <div class="slider-content" v-for="catalog in products" :key="catalog.id">
                <div class="text-wrapper text-center" :class="catalog.class">
                  <h2>{{ catalog.title }}</h2>
                </div>
                <div class="texts">
                  <div class="main-text text-center">
                    <h1>{{ catalog.price }}</h1>
                    <h4 :class="catalog.margin">{{ catalog.year }}</h4>
                    <h4>{{ catalog.watch }}</h4>
                  </div>
                  <div class="menu-wrapper text-center">
                    <ul class="text-center menu" :class="catalog.transform">
                      <li>{{ catalog.write }}</li>
                      <li>{{ catalog.list }}</li>
                      <li>{{ catalog.item }}</li>
                      <li>{{ catalog.name }}</li>
                      <li class="active">{{ catalog.text }}</li>
                      <li class="demo" style="display: none">{{ catalog.demo }}</li>
                      <li class="num" style="display: none">{{ catalog.num }}</li>
                      <li class="material" style="display: none">{{ catalog.material }}</li>
                      <li class="texnologic" style="display: none">{{ catalog.texnologic }}</li>
                      <li class="logic" style="display: none">{{ catalog.logic }}</li>
                      <li class="free" style="display: none">{{ catalog.free }}</li>
                    </ul>
                    <button class="catalog-btn text-center" :class="catalog.class" @click="create()">{{ catalog.btn }}</button>
                  </div>
                </div>
              </div>
            </swiper-slide>
          </swiper>
          <swiper :pagination="{clickable: true}" :modules="model" class="mySwiper mobiles">
            <swiper-slide v-for="catalog in mobile_catalog" :key="catalog.id" class="swiper-slide df align-center justify-between">
              <div class="slider-content">
                <div class="text-wrapper text-center" :class="catalog.class">
                  <h2>{{ catalog.title }}</h2>
                </div>
                <div class="texts">
                  <div class="main-text text-center">
                    <h1>{{ catalog.price }}</h1>
                    <h4 :class="catalog.margin">{{ catalog.year }}</h4>
                    <h4>{{ catalog.watch }}</h4>
                  </div>
                  <div class="menu-wrapper text-center">
                    <ul class="text-center menu">
                      <li>{{ catalog.write }}</li>
                      <li>{{ catalog.list }}</li>
                      <li>{{ catalog.item }}</li>
                      <li>{{ catalog.name }}</li>
                      <li class="active">{{ catalog.text }}</li>
                      <li class="demo" style="display: none">{{ catalog.demo }}</li>
                      <li class="num" style="display: none">{{ catalog.num }}</li>
                      <li class="material" style="display: none">{{ catalog.material }}</li>
                      <li class="texnologic" style="display: none">{{ catalog.texnologic }}</li>
                      <li class="logic" style="display: none">{{ catalog.logic }}</li>
                      <li class="free" style="display: none">{{ catalog.free }}</li>
                    </ul>
                    <button class="catalog-btn text-center" :class="catalog.class" @click="create()">{{ catalog.btn }}</button>
                  </div>
                </div>
              </div>
            </swiper-slide>
          </swiper>
        </div>
      </div>
      <div class="popup-bg" v-if="bg_popup" @click="close()"></div>
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
            <select class="form-select form-select-lg mb-3" v-model="cors">
              <option value="" disabled selected>Kurslarimiz...</option>
              <option selected v-for="opt in options" :key="opt">{{ opt }}</option>
            </select>
            <textarea placeholder="Izohlar..." v-model="comment"></textarea>
            <button @click.prevent="send()">{{ btn }}</button>
          </form>
        </div>
      </div>
      <div class="modal modal-js">
        <div class="content-modal">
          <img :src="require('/src/assets/images/Mask Group.png')" alt="Mask Group">
          <h2><span class="spans">Murojaat</span> uchun rahmat</h2>
          <h2>Tez orada siz <span class="spans">bilan</span> bog'lanamiz</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import {Swiper, SwiperSlide} from "swiper/vue";
import {Pagination, Navigation} from "swiper";
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import 'swiper/css/scrollbar';
import axios from "axios";

export default {
  name: "vCatalog",
  data() {
    return {
      title: "Kurslarimiz",
      catalogs: [
        {
          id: 1,
          title: "Подготовка к школе",
          price: "30 000  тг",
          year: "4-6 лет",
          watch: "3 занятия в неделю по 3 ч.",
          write: 'Обучение чтению ',
          list: "Письмо",
          item: "Математика",
          name: "Английский язык",
          text: "Подробнее...",
          demo: "Развитие речи",
          num: "Концентрация внимания",
          material: "Усвоение изучаемого материала",
          texnologic: "Различные техники запоминания",
          logic: "Развитие логико-математического мышления",
          btn: "Выбрать",
          class: "blue"
        },
        {
          id: 2,
          title: "скорочтение",
          price: "27 000  тг",
          year: "6-15 лет",
          watch: "3 занятия в неделю по 1 ч.",
          write: "Увеличение скорости чтения",
          list: "Артикуляция",
          item: "Развитие речи",
          name: "Развитие внимания",
          text: "Подробнее...",
          demo: "Увеличение поля зрения",
          num: "Увеличение словарного запаса",
          material: "Понимание прочитанного",
          texnologic: "Пересказ",
          logic: "Различные техники понимания",
          free: "Пробный урок и диагностика БЕСПЛАТНО",
          btn: "Выбрать",
          class: "purple"
        },
        {
          id: 3,
          title: "ментальная арифметика",
          price: "20 000  тг",
          year: "2 занятия в неделю по 1 ч.",
          write: 'Быстрый счет',
          list: "Развитие высокой концентрации",
          item: "Увеличесние поля зрения",
          name: "Фотографическая память",
          text: "Подробнее...",
          demo: "Пробный урок БЕСПЛАТНО",
          num: "Обучающая платформа в ПОДАРОК",
          btn: "Выбрать",
          class: "green",
          margin: "text-margin"
        },
      ],
      products: [
        {
          id: 1,
          title: "Каллиграфия",
          price: "24 000  тг",
          watch: "3 занятия в неделю по 1 ч.",
          write: 'Развитие памяти',
          list: "Восприятие пространства",
          item: "Прокачивание мелкой моторики",
          name: "Основы грамотного письма",
          text: "Подробнее...",
          btn: "Выбрать",
          class: "yellow"
        },
        {
          id: 2,
          title: "Английский язык",
          price: "18 000  тг",
          watch: "2 занятия в неделю по 1,5 ч.",
          write: "Чтение по правилам",
          list: "Знание 500 новых слов",
          item: "Самостоятельное выполнение домашнего задания",
          text: "Подробнее...",
          btn: "Выбрать",
          class: "violet"
        },
        {
          id: 3,
          title: "Группа продленного дня",
          price: "35 000  тг",
          watch: "5 раз в неделю" +
              "1 смена с 9:00 по 12:00" +
              "2 смена с 14:00 по 17:00",
          write: 'Подготовка к СОР,СОЧ',
          list: "Проработка пробелов в знаниях",
          item: "Индивидуальный подход",
          name: "Выявление сильных сторон ребенка",
          text: "Подробнее...",
          btn: "Выбрать",
          class: "orange",
          transform: "transforms",
        },
      ],
      mobile_catalog: [
        {
        id: 1,
        title: "Подготовка к школе",
        price: "30 000  тг",
        year: "4-6 лет",
        watch: "3 занятия в неделю по 3 ч.",
        write: 'Обучение чтению ',
        list: "Письмо",
        item: "Математика",
        name: "Английский язык",
        text: "Подробнее...",
        demo: "Развитие речи",
        num: "Концентрация внимания",
        material: "Усвоение изучаемого материала",
        texnologic: "Различные техники запоминания",
        logic: "Развитие логико-математического мышления",
        btn: "Выбрать",
        class: "blue"
       },
       {
        id: 2,
        title: "скорочтение",
        price: "27 000  тг",
        year: "6-15 лет",
        watch: "3 занятия в неделю по 1 ч.",
        write: "Увеличение скорости чтения",
        list: "Артикуляция",
        item: "Развитие речи",
        name: "Развитие внимания",
        text: "Подробнее...",
        demo: "Увеличение поля зрения",
        num: "Увеличение словарного запаса",
        material: "Понимание прочитанного",
        texnologic: "Пересказ",
        logic: "Различные техники понимания",
        free: "Пробный урок и диагностика БЕСПЛАТНО",
        btn: "Выбрать",
        class: "purple"
        },
       {
        id: 3,
        title: "ментальная арифметика",
        price: "20 000  тг",
        year: "2 занятия в неделю по 1 ч.",
        write: 'Быстрый счет',
        list: "Развитие высокой концентрации",
        item: "Увеличесние поля зрения",
        name: "Фотографическая память",
        text: "Подробнее...",
        demo: "Пробный урок БЕСПЛАТНО",
        num: "Обучающая платформа в ПОДАРОК",
        btn: "Выбрать",
        class: "green",
        margin: "text-margin"
        },
        {
          id: 4,
          title: "Каллиграфия",
          price: "24 000  тг",
          watch: "3 занятия в неделю по 1 ч.",
          write: 'Развитие памяти',
          list: "Восприятие пространства",
          item: "Прокачивание мелкой моторики",
          name: "Основы грамотного письма",
          text: "Подробнее...",
          btn: "Выбрать",
          class: "yellow"
        },
        {
          id: 5,
          title: "Английский язык",
          price: "18 000  тг",
          watch: "2 занятия в неделю по 1,5 ч.",
          write: "Чтение по правилам",
          list: "Знание 500 новых слов",
          item: "Самостоятельное выполнение домашнего задания",
          text: "Подробнее...",
          btn: "Выбрать",
          class: "violet"
        },
        {
          id: 6,
          title: "Группа продленного дня",
          price: "35 000  тг",
          watch: "5 раз в неделю" +
              "1 смена с 9:00 по 12:00" +
              "2 смена с 14:00 по 17:00",
          write: 'Подготовка к СОР,СОЧ',
          list: "Проработка пробелов в знаниях",
          item: "Индивидуальный подход",
          name: "Выявление сильных сторон ребенка",
          text: "Подробнее...",
          btn: "Выбрать",
          class: "orange",
          transform: "transforms",
        },
      ],
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
      this.modal = true
      this.bg_popup = true
    },
    close() {
      this.modal = false
      this.bg_popup = false
    },
    send() {
      const TOKEN = '5366282965:AAHyyVJ7VrL7xh8ObyRcR8k24ssJ1FBkIlQ'
      const CHAT_ID = "-1001847240275"
      const URI_API = `https://api.telegram.org/bot${TOKEN}/sendMessage`
      let modal = document.querySelector('.modal-js')

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
              this.bg_popup = false
            }, 3000)
          })
          .catch((err) => {
            console.log('htolik yuz berdi', err)
          })
    }
  },
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Navigation],
      model: [Pagination]
    };
  },
}
</script>

<style scoped>
.section {
  position: relative;
  overflow: hidden;
  width: 100%;
  height: 100%;
}
option[value=""][disabled] {
  display: none;
}
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
.content h1 {
  font-weight: 600;
  font-size: 48px;
  color: #000000;
}

.vector-bg img {
  width: 201px;
  height: 200px;
}

.transform {
  transform: translateY(63px);
}

.desktops {
  display: block;
}

.mobiles {
  display: none;
}

.dn {
  display: none;
}

.vector {
  width: 268px !important;
  height: 267px !important;
}

.vector-bg {
  margin: 30px 0;
}

.transforms {
  transform: translateY(-25px);
  height: 34vh!important;
}

.swiper {
  width: 100%;
  height: 100%;
}

.slider-content {
  width: 387px;
  height: 778px;
  background: #FFFFFF;
  box-shadow: 0px 52px 34px -27px rgba(225, 225, 225, 0.15);
  border-radius: 30px;
}

.blue {
  background: #018FA3;
}
.purple {
  background: #955EEA;
}
.green {
  background: #4ECA30;
}
.text-wrapper {
  width: 387px;
  height: 80px;
  border-radius: 30px 30px 0px 0px;
  border: none;
}
.text-wrapper h2 {
  font-weight: 700;
  font-size: 24px;
  text-transform: uppercase;
  color: #FFFFFF;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 8vh;
}
.texts {
  margin-top: 60px;
}

.main-text h4 {
  font-weight: 400;
  font-size: 24px;
  color: #000000;
  margin: 10px 0;
}
.main-text {
  margin: 30px 0 50px;
}
.menu li {
  font-weight: 400;
  font-size: 24px;
  color: #000000;
  padding: 10px 0;
}
.active {
  color: #018FA3!important;
}
.catalog-btn {
  width: 219px;
  height: 68px;
  border-radius: 40px;
  font-weight: 500;
  font-size: 24px;
  text-transform: capitalize;
  color: #FFFFFF;
}
.menu {
  height: 37vh;
}
.text-margin {
  margin: 48px 0 0!important;
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
  width: 400px;
  height: 491px;
  background: #F6FAFF;
  border-radius: 30px;
  border: none;
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
  position: fixed;
  top: 0;
  bottom: 0;
  display: flex;
  align-items: center;
  z-index: 2;
  width: 48%;
}

.popup-bg {
  position: fixed;
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
  width: 61%;
  justify-content: end;
  position: fixed;
  top: 0;
  bottom: 0;
  display: flex;
  align-items: center;
  z-index: 2;
  transform: translateX(-20000px);
}

.actives {
  transition: .6s ease-in-out;
  transform: translateX(0)!important;
}

.spans {
  color: #37afe3!important;
}

.slider {
  transform: translateY(-237px);
}

.swiper-slide {
  justify-content: end;
  width: 1400px;
  margin-left: auto;
}
.slider-content {
  margin: 0 52px 0 15px;
}
.swiper-button-next, .swiper-button-prev {
  color: #000!important;
}
.yellow {
  background: #FFE41B;
}
.violet {
  background: #FF4D94;
}
.orange {
  background: #FFA724;
}

@media(max-width: 700px) {
  .vector-bg {
    display: none;
  }
  .slider{
    transform: translateY(0);
    margin: 40px 0 0;
  }
  .desktops {
    display: none;
  }

  .mobiles {
    display: block;
  }
  .slider-content {
    margin: 0 auto;
    height: 726px;
  }
  .content h1 {
    font-size: 43px;
  }
  .text-wrapper h2{
    height: 10vh;
  }
  .catalog-btn {
    width: 204px;
    height: 49px;
    font-size: 20px;
  }
  .content-modal {
    height: 311px;
    padding: 59px 0;
    width: 388px;
    margin: 0 auto;
  }
  .content-modal img {
    width: 80px;
    height: 82px;
  }

  .content-modal h2 {
    font-size: 18px;
    margin-top: 24px;
  }

  .popup {
    width: 67%;
  }

  .modal {
    width: 100%;
    justify-content: center;
  }

  .content-modal {
    padding: 98px 0;
  }
}

@media(max-width: 600px) {
  .popup {
    width: 85%;
  }
  .modal {
    width: 100%;
  }
}

@media(max-width: 570px) {
  .popup {
    width: 86%;
  }
  .modal {
    width: 100%;
  }
}

@media(max-width: 550px) {
  .popup {
    width: 87%;
  }
  .modal {
    width: 100%;
  }
}

@media(max-width: 520px) {
  .popup {
    width: 88%;
  }
  .modal {
    width: 100%;
  }
}

@media(max-width: 500px) {
  .popup {
    width: 91%;
  }
}

@media(max-width: 480px) {
  .modal {
    width: 100%;
  }
  .popup {
    width: 92%;
  }
}
@media(max-width: 470px) {
  .popup {
    width: 93%;
  }
  .modal {
    width: 100%;
  }
}
@media(max-width: 460px) {
  .text-wrapper {
    width: 351px;
    height: 80px;
    margin: 0 auto;
  }
  .text-wrapper h2 {
    font-size: 19px;
  }
  .slider-content {
    width: 351px;
    height: 726px;
  }
  .content h1 {
    font-size: 31px;
  }
  .menu li {
    font-size: 21px;
  }
  .main-text h4 {
    font-size: 21px;
  }
  .slider-content {
    width: 351px;
    height: 697px;
  }
  .content-modal {
    width: 373px;
  }
  .popup {
    width: 95%;
  }
  .modal {
    width: 100%;
    justify-content: center;
  }
  .form input, .form select, .form textarea {
    width: 307px;
  }
}

@media(max-width: 450px) {
  .popup {
    width: 94.5%;
  }
  .modal {
    width: 100%;
  }
}

@media(max-width: 430px) {
  .popup {
    width: 96.5%;
  }
  .modal {
    width: 100%;
  }
}

@media(max-width: 420px) {
  .popup {
    width: 95%;
  }
  .modal {
    width: 100%;
    justify-content: center;
  }
  .form{
    width: 363px;
  }
}

@media(max-width: 390px) {
  .popup {
    width: 93%;
  }
  .form {
    width: 338px;
  }

  .form input {
    width: 284px;
    height: 60px;
  }

  .modal {
    width: 100%;
    justify-content: center;
  }
  .form input, .form select, .form textarea {
    width: 287px;
  }
  .text-wrapper {
    width: 351px;
    height: 80px;
    margin: 0 auto;
  }
  .slider-content {
    width: 351px;
    height: 726px;
  }
  .content h1 {
    font-size: 31px;
  }
  .menu li {
    font-size: 21px;
  }
  .main-text h4 {
    font-size: 21px;
  }
  .slider-content {
    width: 351px;
    height: 697px;
  }
}
@media(max-width: 375px) {
  .text-wrapper {
    width: 351px;
    height: 80px;
    margin: 0 auto;
  }
  .slider-content {
    width: 313px;
    height: 726px;
  }
  .slider-content {
    width: 351px;
    height: 726px;
  }
  .content h1 {
    font-size: 31px;
  }
  .menu li {
    font-size: 21px;
  }
  .main-text h4 {
    font-size: 21px;
  }
  .slider-content {
    width: 351px;
    height: 697px;
  }

  .content-modal {
    width: 282px;
  }
  .popup {
    width: 95.5%;
  }
  .form {
    width: 338px;
  }

  .form input, .form select, .form textarea {
    width: 284px;
    height: 60px;
  }

  .modal {
    width: 100%;
    justify-content: center;
  }
}
@media(max-width: 360px) {
  .slider-content {
    width: 329px;
    height: 697px;
  }
  .text-wrapper {
    width: 329px;
    height: 80px;
    margin: 0 auto;
  }
}
@media(max-width: 350px) {
  .text-wrapper {
    width: 304px;
    height: 80px;
    margin: 0 auto;
  }

  .text-wrapper h2 {
    font-size: 20px;
    height: 10vh;
  }
}
@media(max-width: 360px) {
  .popup {
    width: 96.9%;
  }
  .modal {
    width: 100%;
  }
}
@media(max-width: 350px) {
  .slider-content {
    width: 303px;
    height: 697px;
  }
  .text-wrapper h2 {
    font-size: 20px;
    height: 16vh;
  }
}


@media(max-height: 880px) {
  .text-wrapper h2 {
    height: 10vh;
  }
}

@media(max-height: 750px) {
    .menu {
      height: 37vh;
    }
  .text-wrapper h2 {
    height: 12vh;
  }
}

@media(max-height: 620px) {
  .menu {
    height: 44vh;
  }
}


@media(max-height: 550px) {
  .menu {
    height: 51vh;
  }
}

@media(max-height: 480px) {
  .menu {
    height: 58vh;
  }
}

@media(max-height: 690px) {

  .text-wrapper h2 {
    height: 13vh;
  }
}

@media(max-height: 560px) {
  .text-wrapper h2 {
    height: 17vh;
  }
}

@media(max-height: 390px) {
  .text-wrapper h2 {
    height: 21vh;
  }
}
</style>