<template>
  <div class="play">
    <!-- SEZIONE SCALATA -->
    <div class="section-progress">
      <!-- Aiuti da casa  -->
      <div class="d-flex flex-wrap justify-content-around py-4">
        <div class="help">Aiuto da casa</div>
        <div class="help">50 : 50</div>
      </div>
      <!-- Scalata per il Milione -->
      <ul class="d-flex flex-column flex-wrap">
        <li
          v-for="(jackpot, index) in jackpots"
          :key="index"
          class="text-center mx-3"
        >
          {{ jackpot }} &euro;
        </li>
      </ul>
    </div>
    <!-- SEZIONE DOMANDE  -->
    <div class="section-question">sezione Domande</div>
  </div>
</template>

<script>
export default {
  name: "StartTheGame",
  data() {
    return {
      jackpots: [
        "500",
        "3.000",
        "20.000",
        "70.000",
        "150.000",
        "300.000",
        "1.000.000",
      ],
    };
  },
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
    .help {
      padding: 5px 10px 5px 10px;
      border: 2px solid white;
      border-radius: 90px;
      background-color: orange;
      cursor: pointer;
    }
  }
  .section-question {
    border: 1px dashed red;
    flex-grow: 2;
  }
}
</style>