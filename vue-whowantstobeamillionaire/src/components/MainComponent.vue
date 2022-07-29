<template>
  <div class="container-main">
    <!-- SCHERMATA INIZIALE -->
    <HomeScreen v-if="!start" :start="start" @onChangeBoolean="changeValue" />
    <!-- SCHERMATA GIOCO AVVIATO  -->
    <StartTheGame
      v-else
      :questionEasy="questionEasy"
      :questionMedium="questionMedium"
      :questionHard="questionHard"
    />
  </div>
</template>

<script>
import question from "@/assets/data/logic.json";
import HomeScreen from "./HomeScreen.vue";
import StartTheGame from "./StartTheGame.vue";

export default {
  name: "MainComponent",
  data() {
    return {
      question,
      start: false,
      questionEasy: [],
      questionMedium: [],
      questionHard: [],
    };
  },
  components: {
    HomeScreen,
    StartTheGame,
  },
  mounted() {
    this.questionEasy = this.question.filter((item) => item.level === "Facile");
    this.questionMedium = this.question.filter(
      (item) => item.level === "Medio"
    );
    this.questionHard = this.question.filter(
      (item) => item.level === "Difficile"
    );
    // console.log("facile", this.questionEasy);
    // console.log("medio", this.questionMedium);
    // console.log("difficile", this.questionHard);
  },
  methods: {
    changeValue(boolean) {
      boolean = true;
      this.start = boolean;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.container-main {
  height: calc(100vh - 332px);
  background-color: #11093a;
}
</style>