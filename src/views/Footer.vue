<template>
  <div class="footer">
      <p>
          本站没有监管，请随意说垃圾话
      </p>
      <p>
          参与装修灵堂：<button class="btn" @click="See('https://github.com/Coceki/anti-kiryuucoco-vue')">Github</button><br>
          作者：Coceki (佰陌梓Momoshi)
      </p>
  </div>
</template>

<script>
export default {
    methods:{
        See(e){
            window.location.href = e;
        }
    }
}
</script>

<style scope>
.footer{
    background-color: black;
    position: relative;
    align-items: flex-start;
    left: 0;
    bottom: 0;
    color: white;
    padding:20px
}
</style>