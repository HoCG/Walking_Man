<template>
  <div class="walking-man">
    <div class="man-body">
      <div class="man-body__container">
        <div class="man-head">
          <div class="man-hear"></div>
          <div class="man-face">
            <div class="man-eye"></div>
            <div class="man-mouth"></div>
          </div>
        </div>
        <div class="left-hand">
          <div class="left-cloth"></div>
        </div>
        <div class="middle-part">
          <div class="middle-part__top"></div>
          <div class="middle-part__bottom"></div>
        </div>
        <div class="right-hand">
          <div class="right-cloth"></div>
        </div>
      </div>
      <div class="left-leg">
        <div class="left-shoe"></div>
      </div>
      <div class="right-leg">
        <div class="left-shoe"></div>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "HomeView",
});
</script>
<style>
.walking-man {
  position: relative;
  background: #fff;
  width: 700px;
  height: 150px;
  margin: 50px auto;
  text-align: center;
}

.man-eye {
  width: 6px;
  height: 6px;
  border-radius: 100px;
  top: 3px;
  left: 12px;
  background: #000;
  position: absolute;
}

.man-mouth {
  width: 15px;
  height: 10px;
  border-radius: 0 0 100px 0;
  top: 18px;
  left: 12px;
  background: red;
  position: absolute;
}

.man-head {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: #000;
  position: absolute;
  margin-top: 32.5px;
  margin-left: -22.5px;
}

.man-face {
  margin-left: 17.5px;
  width: 32.5px;
  height: 32.5px;
  position: absolute;
  border-radius: 0 0 50% 0;
  background-color: #fbebcd;
}

.man-hear {
  width: 60px;
  height: 17.5px;
  border-radius: 100px 100px 0 0;
  background: #000;
}

.middle-part {
  z-index: 1;
  background: linear-gradient(yellow 80%, #000 20%);
  height: 100px;
  width: 25px;
  position: absolute;
  margin-top: 95px;
  margin-left: -12.5px;
  border-radius: 100%;
  transform: scale(2.2, 1.3);
}
.left-hand,
.right-hand {
  margin-top: 95px;
  margin-left: -12.5px;
  height: 125px;
  width: 12.5px;
  border-radius: 0 0 100px 100px;
  background-color: #fbebcd;
  float: left;
}

.left-hand {
  position: relative;
  z-index: 9999;
}

.right-hand {
  position: relative;
  z-index: -9999;
}

.left-cloth,
.right-cloth {
  height: 100px;
  width: 12.5px;
  background: yellow;
  position: absolute;
}

.left-shoe,
.right-shoe {
  top: 110px;
  width: 40px;
  height: 20px;
  background: skyblue;
  border-radius: 0 100px 30px 0;
  position: absolute;
}

.left-leg,
.right-leg {
  margin-top: 200px;
  margin-left: -7.5px;
  height: 125px;
  width: 12.5px;
  background: #000;
  float: left;
}
.left-hand,
.right-leg {
  transform-origin: 0 0;
  animation: movement1 0.5s alternate infinite ease-out;
}
.right-hand,
.left-leg {
  transform-origin: 0 0;
  animation: movement2 0.5s alternate infinite ease-in;
}

/* for movement 1 */
@keyframes movement1 {
  from {
    -webkit-transform: rotate(-35deg);
  }
  to {
    -webkit-transform: rotate(20deg);
  }
}

/* for movement 2 */
@keyframes movement2 {
  from {
    -webkit-transform: rotate(20deg);
  }
  to {
    -webkit-transform: rotate(-35deg);
  }
}
.man-body {
  animation: ManBody 6s infinite linear;
  left: 0;
  position: absolute;
}
@keyframes ManBody {
  0% {
    /* 시작 */
    left: 0;
    transform: rotateY(0deg);
  }
  49.9999% {
    /*종료 */
    left: 100%;
    transform: rotateY(0deg);
  }
  50% {
    /*종료 */
    left: 100%;
    transform: rotateY(180deg);
  }
  99.9999% {
    /*종료 */
    left: 0;
    transform: rotateY(180deg);
  }
  100% {
    /*종료 */
  }
}
</style>
