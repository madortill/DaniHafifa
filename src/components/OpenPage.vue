<template>
  <div class="open-page">
    <div class="container" v-if="!toShow">
      <div class="headline">לומדת פיצוץ מטאורים</div>
      <img
        class="arrow"
        @click="next"
        src="@/assets/pictures/arrow.svg"
        alt="arrow"
      />
    </div>

    <div v-if="toShow" class="loading">
      <img
        class="shhh-amongus"
        src="@/assets/pictures/shhh.svg"
        alt="shhh-amongus"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "open-page",
  data() {
    return {
      toShow: false,
    };
  },
  methods: {
    next() {
      this.toShow = true;
      setTimeout(() => {
        this.$emit("next");
      }, 3800);
    },
  },
};
</script>

<style scoped>
body {
  width: 100vw;
  height: 100vh;
}

.open-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100%;
  z-index: 1;
  position: relative;
}

.headline {
  font-family: bn pixeliom;
  color: white;
  font-size: 7rem;
  text-align: center;
}

.arrow {
  width:  8rem;
  height: 6rem;
  position: relative;
  animation: float 2s linear infinite;
}

.container {
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-evenly;
}

@keyframes float {
    0% {
    bottom:0%;
  }
  50% {
    bottom: -3%;
  }
  100% {
    bottom: 0%;
  }
}

@-webkit-keyframes float {
  0% {
    bottom: 5%;
  }
  50% {
    bottom: 8%;
  }
  100% {
    bottom: 5%;
  }
}

.shhh-amongus {
  width: 20rem;
  height: 20rem;
  /* position: absolute;
  top: 30%;
  left: 5%; */
  animation: spin 2s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

@-webkit-keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
