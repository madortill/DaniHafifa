<template>
  <div id="what-is-a-meteor">
    <div class="space-right">
      <img v-if="showCloseBtn" @click="close" class="close" src="@/assets/pictures/X.svg" alt="x"/>
<p class="headline">מהו אסטרואיד?</p>
    <p>
      יצור מרושע שמטרתו להשמיד את כדור הארץ ואנחנו בברוגז איתו ממש.
    </p>
    <button :style="{'--chosen-color': color}" @click="toShow" :class="{'after-press': isPressed}" class="description-btn">תיאור</button>
    <p v-show="showInfo">נראה כמו כדור עגול כזה אבל לא חלק כי יש לו בליטות מכוערות שנראות כמו חצ'קונים.
</p>
    </div>
    
  </div>
</template>

<script>
export default {
  name: "what-is-a-meteor",
  components: {},
  props: ["color"],
  data() {
    return {
      showInfo: false,
      showCloseBtn: false,
      isPressed: false,
    };
  },
  methods: {
    toShow() {
      this.showInfo = true;
      this.isPressed = true;
      this.showCloseBtn = true;
    },
    close() {
      this.$emit('close');
    },
  },
};
</script>

<style scoped>
body {
  width: 100vw;
  height: 100vh;
  position: absolute;
  top: 0%;
  

}

#what-is-a-meteor {
  background-color: black;
  border: 3px solid white;
  border-radius: 3rem;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 29rem;
  height: 55rem;
   direction: rtl;
   font-size: 3.6rem;
}

.headline {
  font-family: bn pixeliom;
  font-size: 3.6rem;
  margin: 0rem;
}

.description-btn {

  border-radius: 1rem ;
  border-color: var(--chosen-color);
    background-color: var(--chosen-color);
    padding: 4vw;
    color: white;
    font-family: BN Pinky;
    font-size: 5vh;
}

.after-press {
   border: 3px solid var(--chosen-color);
    background-color: black;
    color: var(--chosen-color);
}
.space-right {
  position: absolute; 
    right: 3%;
    left: 3%;
    top:6%;
  }

.close {
  position: absolute;
    right: 1rem;
    top: -2.3rem;
        width: 3rem;
}
</style>
