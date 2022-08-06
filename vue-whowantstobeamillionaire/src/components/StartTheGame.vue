<template>
  <div class="play">
    <!-- SEZIONE SCALATA -->
    <div class="section-progress scale-up-ver-center">
      <!-- Aiuti da casa  -->
      <div class="d-flex flex-wrap justify-content-around py-4">
        <div class="help">Aiuto da casa</div>
        <div class="help">50 : 50</div>
      </div>
      <!-- Scalata per il Milione -->
      <ul class="d-flex flex-column flex-wrap">
        <li
          v-for="(jackpot, indexJackpot) in jackpots"
          :key="indexJackpot"
          :class="[
            'text-center',
            'mx-3',
            { correct: stepProgress === indexJackpot },
          ]"
        >
          {{ jackpot }} &euro;
        </li>
      </ul>
    </div>
    <!-- SEZIONE DOMANDE  -->
    <div class="section-question">
      <div class="container-question scale-up-hor-right">
        <div v-for="(item, index) in question" :key="item + index">
          <h4 v-if="playerProgress === index" class="question background-logo">
            {{ item.question }}
          </h4>
          <!-- Container delle risposte  -->
          <div v-if="playerProgress === index" class="answer">
            <div
              :class="[
                'single-answer',
                'col-5 background-logo',
                { 'animate-flicker': typeAnswer == indiceElemento },
              ]"
              v-for="(answer, indiceElemento) in item.answer"
              :key="indiceElemento"
              @click="clickedAnswer(answer, index, indiceElemento)"
            >
              <p>
                {{ answer }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "StartTheGame",
  props: {
    questionEasy: Array,
    questionMedium: Array,
    questionHard: Array,
  },
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
      currentQuestion: 0,
      playerProgress: 0,
      question: [],
      typeAnswer: null,
      stepProgress: null,
    };
  },
  mounted() {
    this.startGame();
  },
  methods: {
    startGame() {
      // this.questionEasy[Math.floor(Math.random() * this.questionEasy.length)];
      while (this.question.length < 3) {
        let stepEasy =
          this.questionEasy[
            Math.floor(Math.random() * this.questionEasy.length)
          ];
        if (!this.question.includes(stepEasy)) {
          this.question.push(stepEasy);
        }
      }
      while (this.question.length < 5) {
        let stepMedium =
          this.questionMedium[
            Math.floor(Math.random() * this.questionMedium.length)
          ];
        if (!this.question.includes(stepMedium)) {
          this.question.push(stepMedium);
        }
      }
      while (this.question.length < 7) {
        let stepHard =
          this.questionHard[
            Math.floor(Math.random() * this.questionHard.length)
          ];
        if (!this.question.includes(stepHard)) {
          this.question.push(stepHard);
        }
      }
      console.log(this.question);
    },
    clickedAnswer(answer, indexObject, indiceAnswer) {
      console.log(indiceAnswer);
      if (answer === this.question[indexObject].correctAnswer) {
        console.log("risposta esatta");
        this.typeAnswer = indiceAnswer;
        this.stepProgress = indexObject;
      } else {
        console.log("risposta sbagliata Gioco Terminato");
        this.typeAnswer = indiceAnswer;
      }
    },
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
    .container-question {
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      text-align: center;
      .question {
        border: 1px solid white;
        padding: 5px 0 !important;
        border-radius: 90px;
        margin: 0px 5px 0px 5px !important;
      }
      .answer {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        justify-content: space-around;
        row-gap: 20px;
        padding-top: 50px;
        .single-answer {
          border: 1px solid white;
          padding: 5px 0;
          border-radius: 90px;
          p {
            cursor: pointer;
          }
        }
      }
    }
  }
}
</style>