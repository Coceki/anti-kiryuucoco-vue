<template>
  <div>
    <topbar></topbar>
    <home></home>
    <Footer></Footer>
  </div>
</template>

<script>
import home from './views/Home.vue'
import topbar from './views/Topbar.vue'
import Footer from './views/Footer'
export default {
  name: 'App',
  components: {
    home,
    topbar,
    Footer
  }
}
</script>

<style>
        @font-face{
          font-family: 'Xingkai';
          src: url('./font/STXINGKA.TTF') format('truetype');
        }
        body{
          margin: 0;
          overflow-x:hidden;

        }
        .grid-container {
            /*网格容器*/
            width: 100%;
            
        }
        .row::after,
        .row::before {
            /*行*/
            content: "";
            display: block;
            clear: both;
            height: 0;
            overflow: hidden;
        }
        
        .col-1 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 6.25%;
        }
        .col-2 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 12.5%;
        }
        .col-3 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 18.75%;
        }
        .col-4 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 25%;
        }
        .col-5 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 31.25%;
        }
        .col-6 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 37.5%;
        }
        .col-7 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 43.75%;
        }
        .col-8 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 50%;
        }
        .col-9 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 56.25%;
        }
        .col-10 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 62.5%;
        }
        .col-11 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 68.75%;
        }
        .col-12 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 75%;
        }
        .col-13 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 81.25%;
        }
        .col-14 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 87.5%;
        }
        .col-15 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 93.75%;
        }
        .col-16 {
            /*列*/
            float: left;
            min-width: 1px;
            width: 100%;
        }
</style>
