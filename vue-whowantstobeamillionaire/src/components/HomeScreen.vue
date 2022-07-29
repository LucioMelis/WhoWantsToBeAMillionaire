<template>
  <div class="start pt-5">
    <div>
      <h2 class="focus-in-contract-bck">
        Benvenuto a Chi Vuol Essere Milionario!
      </h2>
      <h4 class="focus-in-contract-bck">Clicca per iniziare il gioco</h4>
      <div class="mt-5">
        <button
          @click="$emit('onChangeBoolean', start)"
          class="btn lm-btn rotate-scale-down"
        >
          Inizia il Gioco
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeScreen",
  props: {
    start: Boolean,
  },
};
</script>

<style lang="scss" scoped>
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