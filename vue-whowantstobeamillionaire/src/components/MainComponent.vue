<template>
  <div class="container-main">
    <!-- SCHERMATA INIZIALE -->
    <div class="start pt-5" v-if="!startGame">
      <div>
        <h2 class="focus-in-contract-bck">
          Benvenuto a Chi Vuol Essere Milionario!
        </h2>
        <h4 class="focus-in-contract-bck">Clicca per iniziare il gioco</h4>
        <div class="mt-5">
          <button
            @click="startGame = true"
            class="btn lm-btn rotate-scale-down"
          >
            Inizia il Gioco
          </button>
        </div>
      </div>
    </div>
    <!-- SCHERMATA GIOCO AVVIATO  -->
    <div v-else class="play">
      <!-- SEZIONE SCALATA -->
      <div class="section-progress">
        <!-- Aiuti da casa  -->
        <div class="d-flex flex-wrap justify-content-around py-4">
          <button class="btn lm-btn">Aiuto da casa</button>
          <button class="btn lm-btn">50 : 50</button>
        </div>
        <!-- Scalata per il Milione -->
        <ul>
          <li>500 &euro;</li>
          <li>3.000 &euro;</li>
          <li>20.000 &euro;</li>
          <li>70.000 &euro;</li>
          <li>150.000&euro;</li>
          <li>300.000 &euro;</li>
          <li>1.000.000 &euro;</li>
        </ul>
      </div>
      <!-- SEZIONE DOMANDE  -->
      <div class="section-question">sezione Domande</div>
    </div>
  </div>
</template>

<script>
import question from "@/assets/data/logic.json";

export default {
  name: "MainComponent",
  data() {
    return {
      question,
      startGame: false,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.container-main {
  height: calc(100vh - 332px);
  background-color: #11093a;
  .start {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    // Prova colore sezioni da eliminare
    justify-content: center;
    text-align: center;
    // Animazioni
    .focus-in-contract-bck {
      -webkit-animation: focus-in-contract-bck 2s
        cubic-bezier(0.25, 0.46, 0.45, 0.94) both;
      animation: focus-in-contract-bck 1s cubic-bezier(0.25, 0.46, 0.45, 0.94)
        both;
    }
    .rotate-scale-down {
      -webkit-animation: rotate-scale-down 0.2s linear both;
      animation: rotate-scale-down 1s linear both;
    }
  }
  .play {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    // Prova colore sezioni da eliminare
    color: white;
    .section-progress {
      border: 1px dashed red;
      flex-grow: 1;
    }
    .section-question {
      border: 1px dashed red;
      flex-grow: 2;
    }
  }
}

// Keyframes Intro
@-webkit-keyframes focus-in-contract-bck {
  0% {
    letter-spacing: 1em;
    -webkit-transform: translateZ(300px);
    transform: translateZ(300px);
    -webkit-filter: blur(12px);
    filter: blur(12px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateZ(12px);
    transform: translateZ(12px);
    -webkit-filter: blur(0);
    filter: blur(0);
    opacity: 1;
  }
}
@keyframes focus-in-contract-bck {
  0% {
    letter-spacing: 1em;
    -webkit-transform: translateZ(300px);
    transform: translateZ(300px);
    -webkit-filter: blur(12px);
    filter: blur(12px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateZ(12px);
    transform: translateZ(12px);
    -webkit-filter: blur(0);
    filter: blur(0);
    opacity: 1;
  }
}
// Keyframe button
@-webkit-keyframes rotate-scale-down {
  0% {
    -webkit-transform: scale(1) rotateZ(0);
    transform: scale(1) rotateZ(0);
  }
  50% {
    -webkit-transform: scale(0.5) rotateZ(180deg);
    transform: scale(0.5) rotateZ(180deg);
  }
  100% {
    -webkit-transform: scale(1) rotateZ(360deg);
    transform: scale(1) rotateZ(360deg);
  }
}
@keyframes rotate-scale-down {
  0% {
    -webkit-transform: scale(1) rotateZ(0);
    transform: scale(1) rotateZ(0);
  }
  50% {
    -webkit-transform: scale(0.5) rotateZ(180deg);
    transform: scale(0.5) rotateZ(180deg);
  }
  100% {
    -webkit-transform: scale(1) rotateZ(360deg);
    transform: scale(1) rotateZ(360deg);
  }
}
</style>