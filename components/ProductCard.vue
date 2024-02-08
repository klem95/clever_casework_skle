<template lang="">
  <div class="cardContainer" @click="selectItem">
    <img :src="fullImageUrl" alt="answerthumb" class="" />
    <div class="textContainer">
      <p class="coloredText recommendation">Vi vil anbefale</p>
      <p class="coloredText productTitle">{{ productTitle }}</p>
      <p class="productDescription coloredText">{{ productDescription }}</p>
    </div>
    <div class="buttonContainer">
      <button class="buttonGreen" @click="navigateTo('/')">
        Se {{ productTitle }}
      </button>
      <button class="buttonWhite" @click="navigateTo('/privat-ladeloesninge')">
        Prøv på ny
      </button>
    </div>
  </div>
</template>
<script>
export default {
  props: ["imageUrl", "productTitle", "productDescription"],
  computed: {
    fullImageUrl() {
      const path = "../images/resultImages/";
      return path + this.imageUrl;
    },
  },
};
</script>
<style scoped>
.cardContainer {
  display: flex;
  padding: 24px;
  flex-direction: column;
  align-items: flex-start;
  flex: 1 0 0;
  border: 1px solid var(--Green-Tint20, #ccd7d6);
  background: var(--White, #fff);
  transition: transform 0.4s ease;
  max-width: 560px;
}

img {
  width: 100%;
  height: auto;
}
.textContainer {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-self: stretch;
  color: var(--Green, #003732);
  text-align: center;
}

button {
  width: 100%;
  padding: 8px 32px;
  justify-content: center;
  align-items: center;
}

.buttonGreen {
  background: var(--primary-color-green);
  color: #ffffff;
  transition: opacity 0.4s ease;
  font-weight: 50;
}

.buttonGreen:hover {
  opacity: 0.8;
}

.buttonWhite {
  background: var(--White, #fff);
  transition: background-color 0.4s ease;
  font-weight: 50;
}
.buttonWhite:hover {
  background: var(--green-tint-5);
}

.buttonContainer {
  width: 100%;
}
.productDescription {
  margin-top: 32px;
  margin-bottom: 40px;
  text-align: center;
  font-family: "No5Gx";
  font-size: 15px;
  font-style: normal;
  font-weight: 50;
  line-height: 150%; /* 22.5px */
}
.coloredText {
  color: var(--primary-color-green);
}

.productTitle {
  text-align: center;
  font-family: "No5Gx";
  font-size: 36px;
  font-style: normal;
  font-weight: 30;
  line-height: 140%; /* 50.4px */
}
.recommendation {
  text-align: center;
  font-family: "No5Gx";
  font-size: 15px;
  font-style: normal;
  font-weight: 200;
  line-height: 150%; /* 22.5px */
}
</style>
