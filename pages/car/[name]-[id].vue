<script setup>
const route = useRoute();

const { totTitleCase } = useUtilities();

useHead({
  title: `${totTitleCase(route.params.name)}`,
  description: "Find the best value on cars deals in your city",
});

definePageMeta({
  layout: "custom",
});
</script>

<template>
  <div>
    <CarDetailHero />

    <CarDetailAttributes />

    <CarDetailDescription />

    <CarDetailContact />
  </div>
</template>
