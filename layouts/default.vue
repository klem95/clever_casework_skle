<template>
  <div>
    <header class="headerContainer">
      <nav class="flex justify-between">
        <div class="flex-none">
          <ul class="flex gap-8">
            <li>
              <NuxtLink class="navItemPages navItem" to="/"
                >Privatkørsel</NuxtLink
              >
            </li>
            <li>
              <NuxtLink class="navItemPages navItem" to="/">Erhverv</NuxtLink>
            </li>
            <li>
              <NuxtLink class="navItemPages navItem" to="/"
                >Boligforeninger</NuxtLink
              >
            </li>
          </ul>
        </div>
        <div class="flex justify-center items-center">
          <img
            class="cleverIcon"
            src="/images/text/clever_white.svg"
            alt="cleverTitle"
          />
        </div>
        <div class="flex gap-1">
          <img src="/images/icons/bulbWhite.svg" />
          <NuxtLink class="navItem navItemPages" to="/"
            >Spørgsmål og svar</NuxtLink
          >
        </div>
      </nav>
    </header>
    <slot />
  </div>
</template>

<script></script>

<style scoped>
.navItemPages {
  text-align: center;
  font-family: "No5";
  font-size: 15px;
  font-style: normal;
  font-weight: 400;
  line-height: 150%; /* 22.5px */
}

.navItem {
  color: var(--White, #fff);
}
.headerContainer {
  padding: 24px 48px;
  position: absolute;
  width: 100%;
}
.cleverIcon {
  align-self: "stretch";
}
</style>
