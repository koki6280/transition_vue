<template>
  <div class="main">
     <button @click="show = !show">切り替え</button>
     <transition 
       enter-active-class="animate__animated animate__bounce"
       leave-active-class="animate__animated animate__shakeX"
       appear
     >
       <p v-if="show">hello</p>
     </transition>
     <transition 
       name="slide" 
       type="animation"
       appear
     >
       <p v-if="show">bye</p>
     </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: true
    };
  }
};
</script>

<style scoped>
.fada-enter {
  opacity: 0;
}
.fada-enter-active {
  transition: opacity 0.5s;
}
.fada-enter-to {
  opacity: 1;
}
.fada-leave {
  opacity: 1;
}
.fada-leave-active {
  transition: opacity 0.5s;
}
.fada-leave-to {
  opacity: 0;
}

.slide-enter,
.slide-leave-to {
   opacity: 0;
}
.slide-enter-active {
   animation: slide-in 0.5s;
   transition: opacity 1s;
}

.slide-leave-active {
   animation: slide-in 0.5s reverse;
   transition: opacity 1s;
}


@keyframes slide-in {
  from {
    transform: translateX(100px);
  }
  to {
    transform: translateX(0);
  }
}


.main {
  width: 70%;
  margin: auto;
  padding-top: 5rem;
  text-align: center;
}

</style>