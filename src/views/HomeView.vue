<template>
  <div class="preloader-video">
    <video width="900" autoplay muted>
      <source :src="require('/src/assets/fajr_1.mp4')" type="video/mp4">
    </video>
  </div>
  <div class="home">
    <header>
      <Menu />
      <MainMenu />
    </header>
    <main>
      <div class="product">
        <Product />
      </div>
      <div class="direction">
        <Direction />
      </div>
      <div class="catalog">
         <Catalog />
      </div>
      <div class="certificate">
        <Certificate />
      </div>
      <div class="comment">
        <Comments />
      </div>
      <div class="contact">
        <Contact />
      </div>
      <div class="maps">
        <Maps />
      </div>
    </main>
    <footer>
      <Footer />
    </footer>
  </div>
</template>

<script>
import Menu from "@/components/menu/Menu";
import MainMenu from "@/components/menu/MainMenu";
import Product from "@/components/main/Product";
import Direction from "@/components/main/Direction";
import Catalog from "@/components/main/Catalog";
import Certificate from '@/components/main/Certificate'
import Comments from "@/components/main/Comments";
import Contact from "@/components/main/Contact";
import Maps from "@/components/main/Maps";
import Footer from "@/components/footer/Footer";
import $ from 'jquery'
export default {
  name: 'HomeView',
  mounted() {
    let home = document.querySelector('.home')
    home.style.display = 'none'
    function preloader() {

      $(() => {

        setInterval(() => {
          let p = $('.preloader-video');

          p.css('opacity', 0)

          setInterval(
              () => p.remove(), home.style.display = 'block',
              parseInt(p.css('--duration')) * 30000
          );

        }, 1000);
      });
    }
    setInterval(() => preloader(), 2800);
  },
  components: {
    Menu,
    MainMenu,
    Product,
    Direction,
    Catalog,
    Certificate,
    Comments,
    Contact,
    Maps,
    Footer
  }
}
</script>
<style scoped>
  .catalog {
    background: #F6FAFF;
    padding: 50px 0 0;
  }


  .preloader-video {
    --duration: 1s;
    position: fixed;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: var(--duration);
  }

  .contact {
    padding-top: 82px;
  }
  footer {
    display: flex;
    height: 12vh;
    align-items: end;
  }

  @media(max-width: 1950px) {
    header {
      height: 121vh;
    }
  }
  @media(max-width: 700px) {
    header {
      height: 74vh;
    }
    .product {
      height: 180vh!important;
    }
  }
  @media(max-width: 600px) {
    header {
      padding: 20px 30px;
      height: auto;
    }

    .product {
      margin: 160px 0 0;
      height: 154vh!important;
    }
    .catalog {
      padding: 52px 0;
      margin: 45px 0;
    }
    .contact {
       padding-top: 0;
    }
    .comment {
      margin: 57px 0 0;
    }
    footer {
      height: auto;
    }
  }
  @media screen and (max-width: 600px), screen and (max-height: 650px) {
    .product {
      margin: 160px 0 0;
      height: 184vh!important;
    }
  }
  @media screen and (max-width: 530px), screen and (max-height: 880px) {
    .product {
      height: 175vh!important;
    }

  }
  @media(max-width: 500px) {
    .product {
      height: 137vh!important;
    }
  }
  @media(max-width: 490px) {
    header, .product {
      height: auto;
    }
    .catalog {
      padding: 52px 0;
       margin: 0;
    }
  }
  @media screen and (max-width: 414px),
  screen and(max-height: 896px) {
    header {
      height: auto;
    }
  }
  @media(max-width: 390px) {
    .images img {
      width: 337px;
      height: 289px;
    }
  }
  @media screen and (max-width: 390px) and (max-height: 844px) {
    header, .product {
      height: auto;
    }
  }
  @media screen and (max-width: 390px) and (max-height: 765px) {
    header, .product {
      height: auto;
    }
  }
  @media(max-width: 360px) {
    .product {
      height: 128vh!important;
    }
  }
  @media(max-height: 730px) {
    .product {
      height: 180vh!important;
    }

  }
  @media(max-width: 375px) {

    .product {
      margin: 0;
    }
    header, .product {
      height: auto;
    }
    .catalog {
      padding: 52px 0;
      margin: 0;
    }
  }

  @media(max-height: 560px) {
    .product {
      height: 200vh;
    }

  }
  @media(max-height: 500px) {
    .maps {
      margin: 60px 0 0;
    }
  }
  @media(max-height: 480px) {
    .maps {
      margin: 70px 0 0;
    }
  }
</style>
