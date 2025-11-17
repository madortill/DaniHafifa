<template>
  <div id="finish-page">
    <p class="title">כל הכבוד סיימת את הלומדה בהצלחה!!</p>
    <img class="party" src="/pictures/party.svg" alt="party" />
  </div>
</template>

<script>
export default {
  name: "finish-page",
  components: {},
  data() {
    return {};
  },
  methods: {},
};
</script>

<style scoped>
body {
  width: 100vw;
  height: 100vh;
}

#finish-page {
  width: 100vw;
  height: 100vh;
  position: absolute;
  top: 0%;
  overflow: hidden;
  display: flex;
    flex-direction: column;
    align-items: center;
}

.party {
  height: 40rem;
  width: 40rem;

}

.title {
  font-family: bn pixeliom;
  width: 100vw;
  font-size: 4rem;
  text-align: center;
  direction: rtl;
}
</style>
