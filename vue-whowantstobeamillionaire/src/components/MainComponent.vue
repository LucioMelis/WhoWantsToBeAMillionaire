<template>
  <div class="container-main">
    <div class="container-general">
      <div class="section-progress">sezione scalata</div>
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
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.container-main {
  height: calc(100vh - 332px);
  background-color: #11093a;
  .container-general {
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
      text-align: center;
    }
  }
}
</style>