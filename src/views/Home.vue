<template>
  <div id="innerpage" class="grid-container" style="margin-top:80px">
    <div class="row">
      <div class="col-16" style="text-align:center">
        <div class="hengpi">地之屎众</div>
      </div>
    </div>
    <div class="row">
      <div class="col-4">
        <div class="lian">
          解决后股之忧
        </div>
      </div>
      <div class="col-8">
        <div class="grid-container">
        <div class="row">
          <div class="dian">
            奠
          </div>
        </div>
        <div class="row">
          <div style="text-align:center">
          <img :src="cocoblack" class="cocopic">
          </div>
        </div>
        </div>
      </div>
      <div class="col-4">
        <div class="lian">
          大开方便之门
        </div>
      </div>
    </div>
    <div class="row">
      <div class="tutan">
      来都来了,吐口痰再走吧
      </div>
    </div>
    <div class="row">
      <div class="tutaninput">
      倒垃圾: <input type="text" name="textsend" v-model="Text"><button class="btn ripple" @click="sendText">发送</button>
      </div>
    </div>
    <div class="row">
      <div class="info">
        <p>
          这个网站将会永久运行，以告诫各位有识之士，只懂逐利不懂尊重的企业要让它滚出中国！
          <img :src="antiholo">
        </p>
      </div>
    </div>
  </div>
</template>

<script>

export default {
data: () => ({
cocoblack:require('../assets/Kiryu_Coco_black.png'),
antiholo:require('../assets/antihololive.png'),
Text:null,
channelmax: 40, //默认最大弹道数
channel:39,
Textonline:null
}),
mounted(){
  const axios = require("axios");
  axios.get('http://kiryuucoco.icu/php/read.php')
        .then(response => {
        this.Textonline = response.data;
        console.log(this.Textonline);
        this.showText();
        })
    
},
methods:{
  showText(){
    for(var i in this.Textonline){
    var screen = document.getElementById("innerpage");
    var poptextspan = document.createElement("span");
    var content = document.createTextNode(this.Textonline[i]);
    poptextspan.classList.add("start");
    poptextspan.style.top = String((this.channelmax - this.channel) * 22) + "px";
    poptextspan.style.fontSize = "20px";
    poptextspan.style.color = "black";
    poptextspan.style.textAlign = "left";
    poptextspan.style.position = "absolute";
    poptextspan.style.textShadow = "-2px 2px #FFF";
    poptextspan.style.whiteSpace = "nowrap";
    poptextspan.style.animation = "mov " + String(40 - this.Textonline[i].length * 0.2) + "s";
    poptextspan.appendChild(content);
    screen.appendChild(poptextspan);
    if(this.channel==0){
      this.channel=39
    }else{
      this.channel=this.channel-1;
    }
    setTimeout(()=>{
      screen.removeChild(screen.childNodes[5])
    },(40 - this.Textonline[i].length * 0.2)*1000);
    }
  },
  sendText(){
    if(this.Text!=''){
    var screen = document.getElementById("innerpage");
    var poptextspan = document.createElement("span");
    var content = document.createTextNode(this.Text);
    poptextspan.classList.add("start");
    poptextspan.style.top = String((this.channelmax - this.channel) * 22) + "px";
    poptextspan.style.fontSize = "20px";
    poptextspan.style.color = "black";
    poptextspan.style.textAlign = "left";
    poptextspan.style.position = "absolute";
    poptextspan.style.textShadow = "-2px 2px #FFF";
    poptextspan.style.whiteSpace = "nowrap";
    poptextspan.style.animation = "mov " + String(40 - this.Text.length * 0.2) + "s";
    poptextspan.appendChild(content);
    screen.appendChild(poptextspan);
    if(this.channel==0){
      this.channel=39
    }else{
      this.channel=this.channel-1;
    }
    setTimeout(()=>{
      screen.removeChild(screen.childNodes[5])
    },(40 - this.Text.length * 0.2)*1000);

    }
  }
}
}
</script>

<style scope>
.start {
  animation-timing-function: linear;
  animation: mov 20s;
  -moz-animation: mov 20s; /* Firefox 4 */
  -webkit-animation: mov 20s; /* Safari 和 Chrome */
  -o-animation: mov 20s; /* Opera */
}
@keyframes mov {
  from {
    right: -20%;
  }
  to {
    right: 150%;
  }
}
@-moz-keyframes mov /* Firefox */ {
  from {
    right: -20%;
  }
  to {
    right: 150%;
  }
}
@-webkit-keyframes mov /* Safari 和 Chrome */ {
  from {
    right: -20%;
  }
  to {
    right: 150%;
  }
}
@-o-keyframes mov /* Opera */ {
  from {
    right: -50%;
  }
  to {
    right: 100%;
  }
}
.btn{
  position: relative;
  border-radius: 16px;
  display: inline-block;
  margin: 5px;
  padding: 10px;
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
  color: #fff;
  font-size: 15px;
  align-items: center;
  text-align: center;
  border: 0pt;
  outline: none;
  transition: 0.5s;
  background: linear-gradient(83.54deg, #000000 -7.64%, #303030 145.94%);
    box-shadow: 2px 3px 5px rgba(0, 0, 0, 0.42), -2px -2px 5px rgba(238, 238, 238, 0.6);
    
    
}
.btn:hover {
        box-shadow: 2px 3px 40px rgba(20, 20, 20, 0.42), -2px -2px 16px rgba(0, 0, 0, 0.6)
    }
.btn:active {
        box-shadow: inset 3px 3px 10px rgba(54, 23, 0, 0.295), inset -3px -3px 10px rgba(0, 0, 0, 0.705) !important
    }
.ripple {
  overflow: hidden;
}
.ripple:after {
  content: "";
  display: block;
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  pointer-events: none;
  background-image: radial-gradient(
    circle,
    rgb(255, 255, 255) 10%,
    transparent 10.01%
  );
  background-repeat: no-repeat;
  background-position: 50%;
  transform: scale(10, 10);
  opacity: 0;
  transition: transform 0.4s, opacity 0.6s;
}

.ripple:active:after {
  transform: scale(0, 0);
  opacity: 0.3;
  transition: 0s;
}
input{
    border: 5px solid #ccc; 
    font-size: 25px;
}
.hengpi{
  margin:0 auto;
  padding: 10px;
  font-family: Xingkai;
  font-size: 50px;
  background-color: black;
  color: white;
  max-width: 800px;
  border:15px solid transparent;
  border-image:url('../assets/border.png') 30 30 round;
  letter-spacing:20px;
  
}
.lian{
  margin:0 auto;
  margin-top: 10px;
  padding: 10px;
  padding-top: 50px;
  padding-bottom: 50px;
  font-family: Xingkai;
  font-size: 50px;
  background-color: black;
  color: white;
  width: 50px; 
  border:15px solid transparent;
  border-image:url('../assets/border.png') 30 30 round;
}
.cocopic{
  max-width: 90%;
  max-height: 200px;
}
.dian{
  text-align:center;
  margin:0 auto;
  padding: 20px;
  font-family: Xingkai;
  font-size: 150px;
}
.tutan{
  text-align:center;
  margin:0 auto;
  padding: 20px;
  font-family: Xingkai;
  font-size: 40px;
}
.tutaninput{
  text-align:center;
  margin:0 auto;
  padding: 20px;
  font-family: Xingkai;
  font-size: 30px;
}
.info{
  padding: 20px;
  font-family: Xingkai;
  font-size: 30px;
}
</style>