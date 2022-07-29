<template>
  <div class="play">
    <!-- SEZIONE SCALATA -->
    <div class="section-progress">
      <!-- Aiuti da casa  -->
      <div class="d-flex flex-wrap justify-content-around py-4">
        <button class="btn lm-btn">Aiuto da casa</button>
        <button class="btn lm-btn">50 : 50</button>
      </div>
      <!-- Scalata per il Milione -->
      <div class="d-flex flex-column flex-wrap align-items-center py-5">
        <div>500 &euro;</div>
        <div>3.000 &euro;</div>
        <div>20.000 &euro;</div>
        <div>70.000 &euro;</div>
        <div>150.000&euro;</div>
        <div>300.000 &euro;</div>
        <div>1.000.000 &euro;</div>
      </div>
    </div>
    <!-- SEZIONE DOMANDE  -->
    <div class="section-question">sezione Domande</div>
  </div>
</template>

<script>
export default {
  name: "StartTheGame",
};
</script>

<style lang="scss" scoped>
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
</style>