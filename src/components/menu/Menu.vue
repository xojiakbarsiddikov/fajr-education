<template>
 <div class="container df align-center justify-between">
   <div class="open-btn-wrapper">
     <button class="nav-btn open-btn">
       <i class="fas fa-bars"></i>
     </button>
   </div>
   <div class="images">
     <img :src="require('/src/assets/images/logo (2).png')" alt="fajr-logo">
   </div>
   <div class="menu-wrapper">
     <ul class="menu df align-center">
        <li v-for="menu in menus" :key="menu.id">
          <a :href="`#${menu.path}`" class="list_href">
            <span>{{ menu.list }}</span>
          </a>
        </li>
     </ul>
   </div>
   <div class="top-bar df align-center">
     <button class="btn text-center">
       <i class="fa-solid fa-phone"></i>
     </button>
     <h4>{{ tell }}</h4>
   </div>
   <div class="nav nav-black">
     <div class="nav nav-red">
       <div class="nav nav-white">
         <button class="nav-btn close-btn">
           <i class="fas fa-times"></i>
         </button>
         <div class="images">
           <img :src="require('/src/assets/images/logo (2).png')" alt="logo">
         </div>
         <ul class="list_item">
           <li v-for="menu in menus" :key="menu.id" :class="menu.class">
             <a :href="`#${menu.path}`">
               <span>{{ menu.list }}</span>
             </a>
           </li>
         </ul>
         <div class="top-bar-mobile df align-center">
           <button class="btn text-center">
             <i class="fa-solid fa-phone"></i>
           </button>
           <h4>{{ tell }}</h4>
         </div>
       </div>
     </div>
   </div>
 </div>
</template>

<script>
import $ from 'jquery'
export default {
  name: "vMenu",
  data() {
    return {
      menus: [
        {id: 1, list: "Biz haqimizda", path: "about"},
        {id: 2, list: "Kurslarimiz", path: "catalog"},
        {id: 3, list: "Sertifikatlar", path: "certificate"},
        {id: 4, list: "Fikrlar", path: "comments"},
        {id: 5, list: "Aloqa", path: "contact"},
      ],
      tell: "998  (91) 490-44-04"
    }
  },
  mounted() {
    const open_btn = document.querySelector('.open-btn')
    const close_btn = document.querySelector('.close-btn')
    const nav = document.querySelectorAll('.nav')
    let list = document.querySelectorAll('.list_href')
    let list_item = document.querySelectorAll('.list_item li')
    let body = document.querySelector('#app')

    list.forEach((e) => {
      e.addEventListener('click', () => {
        list.forEach((i) => {
          i.classList.remove('active')
        })
        e.classList.add('active')
      })
    })

    list_item.forEach((e) => {
      e.addEventListener('click', () => {
        list_item.forEach((i) => {
          i.classList.remove('activee')
        })
        e.classList.add('activee')
        nav.forEach(nav_el => nav_el.classList.remove('visible'))
        body.classList.remove('overflows')
        body.style.overflow = 'auto'
        body.style.height = 'auto'
      })
    })

    open_btn.addEventListener('click', () => {
      nav.forEach(nav_el => nav_el.classList.add('visible'))
      body.style.overflow = 'hidden'
      body.style.height = 100 + 'vh'
    })

    close_btn .addEventListener('click', () => {
      nav.forEach(nav_el => nav_el.classList.remove('visible'))
      body.classList.remove('overflows')
      body.style.overflow = 'auto'
      body.style.height = 'auto'
    })



    $('.list').click(function(e){
      e.preventDefault();
      var target = $($(this).attr('href'));
      if(target.length){
        var scrollTo = target.offset().top;
        $('body, html').animate({scrollTop: scrollTo+'px'}, 800);
      }
    });
  }
}
</script>

<style scoped>
  .images img {
    width: 100px;
    height: 38px;
  }

  .nav-black {
    display: none;
  }

  .overflows {
    overflow: hidden;
  }

  .menu li > a{
    font-weight: 500;
    font-size: 16px;
    color: #000000;
    margin: 0 25px;
    padding: 4px 0;
  }
  .open-btn-wrapper {
    display: none;
  }
  .menu li > a:hover {
    color: #37afe3;
    border-bottom: 1px solid #37afe3;
    transition: .2s ease;
  }
  .activee {
    background: #37afe3;
  }
  .btn {
    width: 40px;
    height: 40px;
    background: #37afe3;
    border-radius: 50px;
    color: #fff;
  }
  .top-bar h4, .top-bar-mobile h4 {
    font-weight: 600;
    font-size: 18px;
    color: #000000;
    margin: 0 10px;
  }
  .active {
    border-bottom: 1px solid #37afe3;
    color: #37afe3!important;
  }

  .nav {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 3;
    height: 100vh;
    transform: translateX(-100%);
    transition: transform 0.3s ease-in-out;
  }

  .nav.visible {
    transform: translateX(0);
  }

  .nav-black {
    background-color: rgb(34,31,31);
    width: 100%;
    max-width: 100%;
    height: 100%;
    min-width: 320px;
    transition-delay: 0.4s;
  }

  .nav-red {
    background-color: #37afe3;
    width: 95%;
  }

  .nav-white {
    background-color: #ffff;
    width: 95%;
    padding: 40px;
    position: relative;
  }

  .close-btn {
    position: absolute;
    top: 40px;
    right: 30px;
  }

  .close-btn i {
    color: #000;
  }

  .list_item {
    list-style-type: none;
    padding: 0;
  }

  .list_item li {
    margin: 20px 0;
  }

  .list_item li a {
    color: #000;
    font-size: 16px;
    text-decoration: none;
    text-transform: capitalize;
  }

  .list_item ul {
    list-style-type: none;
    padding-left: 20px;
  }

  .open-btn, .close-btn {
    width: 45px;
    height: 45px;
    border-radius: 50px;
    border: none;
    background: #fff;
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
    font-size: 17px;
  }

  @media(max-width: 1600px) {
    .top-bar {
      z-index: 9;
    }
  }

  @media(max-width: 700px) {
    .menu-wrapper, .top-bar {
      display: none;
    }
    .top-bar-mobile {
      position: absolute;
      bottom: 0;
    }
    .nav-black {
      display: block;
    }
    .list_item li {
      width: 200px;
      padding: 10px;
      border-radius: 8px;
    }
    .open-btn-wrapper {
      display: block;
    }
    .container {
      align-items: end;
    }
  }

</style>