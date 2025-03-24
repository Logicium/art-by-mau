<script setup lang="ts">

import Logo from "@/assets/Logo.vue";
import EmailIcon from "@/assets/EmailIcon.vue";
import FacebookIcon from "@/assets/FacebookIcon.vue";
import InstaIcon from "@/assets/InstaIcon.vue";
import {ref} from "vue";

const section1 = ref("normal");
const section2 = ref("normal");
const section3 = ref("normal");
const section4 = ref("normal");
const section5 = ref("normal");

const singleGrid = ref(false);

const section1Click = function(){
  if(section1.value === "normal"){

    singleGrid.value = true;

    section1.value = "expand";
    section2.value = "contract";
    section3.value = "contract";
    section4.value = "contract";
    section5.value = "contract";
  }else if(section1.value === "expand"){

    singleGrid.value = false;
    section1.value = "normal";
    section2.value = "normal";
    section3.value = "normal";
    section4.value = "normal";
    section5.value = "normal";
  }
}


</script>

<template>
  <div class="home">
    <div class="banner">
      <img class="logo" src="../../public/logo.png" alt="logo"/>
<!--      <Logo/>-->
      <div class="phrase">Beautiful Things with an Artsy Touch</div>
    </div>
    <div class="imageGrid" :class="singleGrid ? 'singleGrid':''">
      <div class="img1" :class="section1" @click="section1Click">
        <div v-if="section1==='expand'" class="imgInfo"></div>
      </div>
      <div class="img2" :class="section2">
        <div v-if="section2==='expand'" class="imgInfo">This piece is called walking in the rain and it is inspired by ... </div>
      </div>
      <div class="img3" :class="section3"/>
      <div class="img4" :class="section4"/>
      <div class="img5" :class="section5">
      </div>

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

.imageArea5{
  background-color: #B5A8D5;
  height: 100%;
  width: 100%;
}

.contract{
  display: none;
  width: 0%;
  transition: 2s linear all;
}

.expand{
  //width: 100%;
  //height: 100%;
  transition: 2s linear all;
  //animation: expand 2s forwards;
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
  //display: flex;
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-gap: 2rem;
  height: 50vh;
  transition: all 2s linear;
}

.singleGrid{
  grid-template-columns: repeat(1, 1fr);
  transition: all 2s linear;
}

.img1,.img2,.img3,.img4,.img5{
  background-size: cover;
  background-position: 100% 100%;
  cursor: pointer;
  transition: all 2s linear;
}

.img1{
  background-image: url("/art1.jpg");
}

.img2{
  background-image: url("/art2.jpg");
}

.img3{
  background-image: url("/art3.jpg");
}

.img4{
  background-image: url("/art4.jpg");
}

.img5{
  background-image: url("/art5.jpg");
}

@keyframes expand {

  from{
    width: 0%;
  }

  to{
    width: 100%;
  }

}

</style>
