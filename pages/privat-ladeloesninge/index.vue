<template>
  <div class="productSelectorContainer justify-items-center">
    <div v-if="!showResult" class="questionContainer">
      <div class="question">
        <h3>{{ productSelections[stepper].question }}</h3>
      </div>
      <div class="cardContainer">
        <OptionCard
          v-for="(option, index) in productSelections[stepper].options"
          :imageUrl="option.imageUrl"
          :answer="option.answer"
          :id="index"
          v-on:listenerChild="listenerChild"
        />
      </div>
    </div>
  </div>
</template>
<script>
definePageMeta({
  layout: "privat-ladeloesninge",
});
export default {
  data() {
    return {
      stepper: 0,
      showResult: false,
      results: [],
      productSelections: [
        {
          id: 0,
          question: "Har du mulighed for at få en ladeboks derhjemme?",
          options: [
            { imageUrl: "homeCharger.svg", answer: "Ja, det har jeg" },
            { imageUrl: "publicCharger.svg", answer: "Nej, det har jeg ikke" },
          ],
        },
        {
          id: 1,
          question: "Hvor forventer du at lade mest?",
          options: [
            { imageUrl: "homeCharger.svg", answer: "Primært hjemme" },
            { imageUrl: "publicCharger.svg", answer: "Mest på farten" },
            { imageUrl: "carOnRoad.svg", answer: "Både ude og hjemme" },
          ],
        },
        {
          id: 2,
          question: "Har du muligheden for at lade på dit arbejde?",
          options: [
            { imageUrl: "workCharger.svg", answer: "Ja" },
            { imageUrl: "parkedCar.svg", answer: "Nej" },
          ],
        },
        {
          id: 3,
          question: "Hvordan ønsker du at betale?",
          options: [
            { imageUrl: "fixedPrice.svg", answer: "Fast beløb" },
            { imageUrl: "flexPrice.svg", answer: "Forbrugsafregnet" },
          ],
        },
      ],
    };
  },
  methods: {
    listenerChild(reply) {
      if (this.stepper < this.productSelections.length - 1) {
        this.results.push({
          questionId: this.productSelections[this.stepper].id,
          anwserId: reply,
        });
        this.stepper++;
      } else {
        const randomProduct = Math.floor(
          Math.random() * this.productSelections.length
        );
        navigateTo("/privat-ladeloesninge/" + randomProduct);
      }
    },
  },
};
</script>
<style>
.productSelectorContainer {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
}

.questionContainer {
  display: flex;
  flex-direction: column;
  row-gap: 32px;
}
.cardContainer {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  column-gap: 16px;
}
.question {
  align-self: center;
  justify-content: center;
}

.resultContainer {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  column-gap: 16px;
}
</style>
