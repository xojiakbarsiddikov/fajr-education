<template>
  <div class="footer">
    <div class="container df align-center justify-between desctopes">
      <div class="images">
        <img :src="require('/src/assets/images/light.png')" alt="fajr-logo">
      </div>
      <div class="menu-wrapper">
        <ul class="menu df align-center">
          <li v-for="menu in menus" :key="menu.id">
            <a :href="`#${menu.path}`" class="list">
              <span>{{ menu.list }}</span>
            </a>
          </li>
        </ul>
      </div>
        <div class="top-bar">
          <a href="https://t.me/acodeuz" target="_blank">
              <img :src="require('/src/assets/images/acode-logo.png')" alt="ds">
          </a>
        </div>
    </div>
    <div class="container mobiles">
      <div class="images df align-center justify-between">
        <img :src="require('/src/assets/images/light.png')" alt="fajr-logo">
        <a href="https://t.me/acodeuz" target="_blank">
          <img :src="require('/src/assets/images/acode-logo.png')" alt="ds">
        </a>
      </div>
      <div class="menu-wrapper">
        <ul class="menu df align-center">
          <li v-for="menu in menus" :key="menu.id">
            <a :href="`#${menu.path}`" class="list">
              {{ menu.list }}
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import $ from "jquery";

export default {
  name: "vFooter",
  data() {
    return {
      menus: [
        {id: 1, list: "Biz haqimizda", path: "about"},
        {id: 2, list: "Kurslarimiz", path: "catalog"},
        {id: 3, list: "Sertifikatlar", path: "certificate"},
        {id: 4, list: "Fikrlar", path: "comments"},
        {id: 5, list: "Aloqa", path: "contact"},
      ],
      tell: "(91) 490-44-04"
    }
  },
  mounted() {
    let list = document.querySelectorAll('.list')

    list.forEach((e) => {
      e.addEventListener('click', () => {
        list.forEach((i) => {
          i.classList.remove('active')
        })
        e.classList.add('active')
      })
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
.footer {
  width: 100%;
  height: 169px;
  background: #0A2530;
}
.images img {
  width: 100px;
  height: 38px;
}

.desctopes {
  display: flex;
}

.mobiles {
  display: none;
}

.menu li > a{
  font-weight: 500;
  font-size: 24px;
  color: #FFFFFF;
  margin: 0 25px;
  padding: 4px 0;
}
.menu li > a:hover {
  color: #37afe3;
  border-bottom: 1px solid #37afe3;
  transition: .2s ease;
}
.btn {
  width: 40px;
  height: 40px;
  background: #37afe3;
  border-radius: 50px;
  color: #fff;
}
.top-bar h4 {
  font-weight: 600;
  font-size: 18px;
  color: #000000;
  margin: 0 10px;
}
.active {
  border-bottom: 1px solid #37afe3;
  color: #37afe3!important;
}
.container {
  width: 100%;
}
.footer {
  display: flex;
  align-items: center;
}
.top-bar img {
  width: 100%;
}
.top-bar {
  width: 8%;
}
@media(max-width: 600px) {
  .menu {
    flex-wrap: wrap;
  }
  .footer {
    height: auto;
    padding: 23px 0;
  }
  .top-bar {
    width: 21%;
  }
  .container {
    width: 84%;
  }
  .menu li > a {
    font-size: 18px;
    padding: 0;
    line-height: 33px;
    margin: 0 25px 0 0;
  }
  .images img {
    width: 146px;
    height: auto;
  }

  .menu-wrapper {
    margin-top: 32px;
  }

  .desctopes {
    display: none;
  }
  .images a > img {
    width: 147px;
    height: auto;
  }
  .mobiles {
    display: block;
  }
}

@media(max-width: 500px) {
  .images img{
    width: 105px;
    height: auto;
  }
  .images a > img {
    width: 130px;
    height: auto;
  }
}
@media screen and (max-width: 350px), screen and (max-height: 480px) {
  .footer {
    margin: 86px 0 0;
  }
}
</style>