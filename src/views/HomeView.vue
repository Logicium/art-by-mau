<script setup lang="ts">

import Logo from "@/assets/Logo.vue";
import EmailIcon from "@/assets/EmailIcon.vue";
import FacebookIcon from "@/assets/FacebookIcon.vue";
import InstaIcon from "@/assets/InstaIcon.vue";
import {ref} from "vue";

const section1 = ref(false);
const section2 = ref(false);
const section3 = ref(false);
const section4 = ref(false);
const section5 = ref(false);

const click = function (){

}

</script>

<template>
  <div class="home">
    <div class="banner">
      <img class="logo" src="../../public/logo.png" alt="logo"/>
<!--      <Logo/>-->
      <div class="phrase">Beautiful Things with an Artsy Touch</div>
    </div>
    <div class="imageGrid">
      <div class="img1" :class="section1 ? 'expand' : '' " @click="section1 = !section1">
        <div v-if="section1" class="imgInfo"></div>
      </div>
      <div class="img2" :class="section2 ? 'expand' : '' " @click="section2 = !section2">
        <div v-if="section2" class="imgInfo">This piece is called walking in the rain and it is inspired by the colors of Raton in spring. </div>
      </div>
      <div class="img3"/>
      <div class="img4"/>
      <div class="img5"/>
    </div>

    <div class="footer">
      <div class="icons">
        <div class="icon"><EmailIcon/></div>
        <div class="icon"><FacebookIcon/></div>
        <div class="icon"><InstaIcon/></div>
      </div>

      <div>Designed by Apotome Labs 2025</div>

    </div>

  </div>

</template>


<style lang="scss" scoped>

.expand{
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
  animation: 1s expand forwards;
}

.imgInfo{
  background-color: rgba(33, 28, 132, 0.8);
  margin-left: auto;
  width: 70%;
  height: 100%;
  color: white;
  padding: 2rem;
}

.icon{
  display: flex;
  align-items: center;
  justify-content: center;
  height: 45px;
  width: 45px;
  background-color: #B5A8D5;
  border-radius: 50%;
  color: #211C84;
  cursor: pointer;
}

.icons{
  align-self: center;
  width: 30%;
  display: flex;
  justify-content: space-between;
  margin-bottom: 1vw;
}

.home{
  display: flex;
  width: 100%;
  align-items: center;
  flex-direction: column;
}

.logo{
  align-self: center;
  background-size: cover;
  background-position: 100% 100%;
  height: 125px;
  filter: sepia(100%) grayscale(100%);
}

.phrase{
  text-align: right;
  margin-top: auto;
  font-size: 2.5vw;
  line-height: 2.5vw;
}

.banner{
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 80%;
  text-align: center;
  font-family: "Urbanist", sans-serif;
  font-size: 4vw;
  height: 20vh;
  background-color: #211C84;
  color:#B5A8D5;
  margin-bottom: 2rem;
}

.footer{
  display: flex;
  padding: 1vw;
  align-items: center;
  flex-direction: column;
  width: 80%;
  margin-top: 2rem;

  background-color: #211C84;
  color: #B5A8D5;
  font-size: 18px;
}

.imageGrid{
  position: relative;
  width: 80%;
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-gap: 2rem;
  height: 50vh;
}

.img1,.img2,.img3,.img4,.img5{
  background-size: cover;
  background-position: 100% 100%;
  cursor: pointer;
  transition: all 2s linear;
  padding: 1rem;
}

.img1{
  background-image: url("public/art1.jpg");
}

.img2{
  background-image: url("public/art2.jpg");
}

.img3{
  background-image: url("public/art3.jpg");
}

.img4{
  background-image: url("public/art4.jpg");
}

.img5{
  background-image: url("public/art5.jpg");
}

@keyframes expand {

  from{
    width: 20%;
  }

  to{
    width: 100%;
  }


}

</style>
