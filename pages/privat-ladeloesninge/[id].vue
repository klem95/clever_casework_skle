<template>
  <div class="resultContainer">
    <ProductCard
      v-if="Object.keys(product).length > 0"
      :imageUrl="product.imageUrl"
      :productTitle="product.title"
      :productDescription="product.description"
    />
  </div>
</template>

<script>
import { useRoute } from "vue-router";
definePageMeta({
  layout: "result",
});
export default {
  setup() {
    const route = useRoute();
    const id = ref(0);
    const productCatalogue = ref([
      {
        id: 0,
        imageUrl: "cleverBox.svg",
        title: "Clever Box",
        description:
          "Vælg Clever Box, hvis du vil eje ladeboksen og betale for det, du lader.",
      },
      {
        id: 1,
        imageUrl: "cleverOne.svg",
        title: "Clever One",
        description: "Lad frit på Danmarks største ladenetværk.",
      },
      {
        id: 2,
        imageUrl: "cleverOneWBox.svg",
        title: "Clever One med ladeboks",
        description:
          "Start dagen med fuld energi fra Clever-ladeboksen hjemme, og lad frit på Danmarks største ladenetværk.",
      },
      {
        id: 3,
        imageUrl: "cleverGo.svg",
        title: "Clever Go",
        description: "Betal for det du lader.",
      },
    ]);
    const product = ref({});

    watch(
      () => route.params,
      (newParams) => {
        id.value = parseInt(newParams.id);
        const foundProduct = productCatalogue.value.find(
          (p) => p.id === id.value
        );
        product.value = foundProduct || {};
      },
      { immediate: true }
    );

    return {
      id,
      product,
    };
  },
};
</script>

<style>
.resultContainer {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
}
</style>
