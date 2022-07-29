<template>
  <div class="container-main">
    <!-- SCHERMATA INIZIALE -->
    <HomeScreen
      v-if="!startGame"
      :startGame="startGame"
      @onChangeBoolean="changeValue"
    />
    <!-- SCHERMATA GIOCO AVVIATO  -->
    <StartTheGame v-else />
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
      startGame: false,
    };
  },
  components: {
    HomeScreen,
    StartTheGame,
  },
  methods: {
    changeValue(boolean) {
      boolean = true;
      this.startGame = boolean;
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