<template>
  <div id="meteors">
    <div v-if="!show" class="space-right">
      <img v-if="showExit" @click="close" class="close" src="pictures/X.svg" alt="x"/>
<p class="headline">- לחצי על מטאור -</p>
    <img @click="meteorInfo('0')" class="baby" src="pictures/meteor.svg" alt="meteor"/>
    <img  @click="meteorInfo('1')" class="teenage" src="pictures/meteor.svg" alt="meteor"/>
    <img @click="meteorInfo('2')" class="adult" src="pictures/meteor.svg" alt="meteor"/>
    </div>
    <info :theColor="color" :type="kind" @back="getBack" v-if="show"></info>
  </div>
</template>

<script>
import Info from './Info.vue';

export default {
  name: "meteors",
  components: {
    Info,
  },
  props: ["color"],
  data() {
    return {
      show: false,
      kind: 0,
      finished: [false ,false ,false],
      showExit: false,
    };
  },
  methods: {
    close() {
      this.$emit('close');
    },
    meteorInfo(type) {
      //if first time in this info
      if(!this.finished[type]) {
        this.finished[type] = true;
      }
        this.show = true;
        this.kind = type;
    },
    getBack() {
         this.show = false;
       let counter =   this.getNumFinished();
         if(counter === 3) {
          this.showExit = true;
         }
    },
  getNumFinished() {
    let counter = 0;
    for( let i = 0; i< this.finished.length; i++) {
      if(this.finished[i]) {
        counter++;
      }
    }
    return counter;
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

#meteors {
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
  font-size: 2.8rem;

}
/* 
.space-right {

  } */

.close {
  position: absolute;
    right: 1rem;
    top: 1rem;
    width: 3rem;
}

.baby {
    width: 25%;
    position: absolute;
    top:20%;
    right: 5%;
    animation: spin 4s linear infinite;
}

.teenage {
    width: 40%;
    position: absolute;
    top:30%;
    left: 10%;
    animation: spin 4s linear infinite;
}

.adult {
    width: 60%;
    position: absolute;
    bottom:10%;
    right: 5%;
    animation: spin 4s linear infinite;
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
