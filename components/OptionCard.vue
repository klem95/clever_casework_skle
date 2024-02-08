<template>
  <transition>
    <div class="cardContainer" @click="selectItem">
      <img :src="fullImageUrl" alt="answerthumb" class="" />
      <div class="textContainer">
        <h4>{{ answer }}</h4>
      </div>
    </div>
  </transition>
</template>
<script>
export default {
  props: ["imageUrl", "answer", "id"],
  data() {
    return {};
  },
  computed: {
    fullImageUrl() {
      const path = "../images/answerImages/";
      return path + this.imageUrl;
    },
  },
  methods: {
    selectItem() {
      this.$emit("listenerChild", this.id);
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
  gap: 32px;
  flex: 1 0 0;
  border: 1px solid var(--Green-Tint20, #ccd7d6);
  background: var(--White, #fff);
  transition: transform 0.4s ease;
  max-width: 324px;
}
img {
  width: 100%;
  height: auto;
}
.textContainer {
  display: flex;
  height: 48px;
  flex-direction: column;
  justify-content: flex-end;
  align-self: stretch;
  color: var(--Green, #003732);
  text-align: center;
}

.cardContainer:hover {
  background: var(--green-tint-5);
  transform: scale(1.05);
  border: 1px solid var(--primary-color-green);
}
</style>
