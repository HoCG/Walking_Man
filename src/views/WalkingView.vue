<template>
  <div id="WalkingMan">
    <div class="ManBody">
      <div class="body">
        <p class="Manhead"></p>
        <p class="Middlepart"></p>
        <p class="Lhand"></p>
        <p class="Rhand"></p>
      </div>
      <p class="LLeg"></p>
      <p class="RLeg"></p>
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
#WalkingMan {
  position: relative;
  background: #fff;
  width: 700px;
  height: 150px;
  margin: 50px auto;
  text-align: center;
}

.Manhead {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: #000;
  position: absolute;
  margin-top: 13px;
  margin-left: -8px;
}

.Middlepart {
  background: #000;
  height: 40px;
  width: 10px;
  position: absolute;
  margin-top: 38px;
  margin-left: -5px;
  border-radius: 100%;
  transform: scale(2.2, 1.3);
}
.Lhand,
.Rhand {
  margin-top: 38px;
  margin-left: -5px;
  height: 50px;
  width: 5px;
  background: #000;
  float: left;
}
.LLeg,
.RLeg {
  margin-top: 80px;
  margin-left: -3px;
  height: 50px;
  width: 5px;
  background: #000;
  float: left;
}
.Lhand,
.RLeg {
  transform-origin: 0 0;
  animation: movement1 0.5s alternate infinite ease-out;
  background: #000;
}
.Rhand,
.LLeg {
  transform-origin: 0 0;
  animation: movement2 0.5s alternate infinite ease-in;
}

/* for movement 1 */
@keyframes movement1 {
  from {
    -webkit-transform: rotate(-40deg);
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
    -webkit-transform: rotate(-40deg);
  }
}
.ManBody {
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
    left: 0%;
    transform: rotateY(180deg);
  }
  100% {
    /*종료 */
  }
}
</style>
