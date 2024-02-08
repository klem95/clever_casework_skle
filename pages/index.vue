import "./styles/style.css";

<template>
  <div class="test">
    <div class="imageContainer">
      <div class="overlay"></div>
    </div>
    <div class="textContainer">
      <p class="strong">Produktvælger</p>
      <h1>Lad os hjælpe dig med at finde den rigtig ladeløsning</h1>
      <p class="context">
        Svar på spørgsmålene og find ud af hvilken Clever løsning der passer
        bedst til dine behov
      </p>
      <button class="buttonTxt" @click="navigateTo('/privat-ladeloesninge')">
        Tag testen her
      </button>
    </div>
  </div>
</template>
<script>
import { useRouter } from "vue-router";

const router = useRouter();

function navigateTo(path) {
  router.push(path);
}
export default {};
</script>

<style>
.test {
  width: 100vw;
  height: 100vh;
  background-color: var(--primary-color-green);
}
.imageContainer {
  width: 100%;
  height: 60vh;
  background: url("/images/rectangle-1.png") lightgray 0% 0% / cover no-repeat;
}

.textContainer {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 32px;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: inherit;
  background: linear-gradient(
    rgba(0, 0, 0, 0.1) 0% 60%,
    var(--primary-color-green)
  );
  pointer-events: none;
}

p,
h1 {
  color: #ffffff;
  text-align: center;
}

button {
  display: flex;
  padding: 8px 32px;
  justify-content: center;
  align-items: center;
  gap: 8px;
  background: var(--White, #fff);
  color: var(--Green, #003732);
}

.buttonTxt {
  transition: opacity 0.4s ease;
}
.buttonTxt:hover {
  opacity: 0.5;
}
.context {
  color: var(--White, #fff);
  text-align: center;
  font-family: "No5Gx";
  font-size: 15px;
  font-style: normal;
  font-weight: 30;
  line-height: 150%; /* 22.5px */
}
</style>
