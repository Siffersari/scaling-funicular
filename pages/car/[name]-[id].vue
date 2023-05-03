<script setup>
const route = useRoute();

useHead({
  title: `${totTitleCase(route.params.name)}`,
  description: "Find the best value on cars deals in your city",
});

definePageMeta({
  layout: "custom",
});

function totTitleCase(str) {
  return str
    .toLowerCase()
    .split(" ")
    .map((word) => word.charAt(0).toUpperCase() + word.slice(1))
    .join(" ");
}
</script>

<template>
  <div>
    <CarDetailHero />

    <CarDetailAttributes />

    <CarDetailDescription />

    <CarDetailContact />
  </div>
</template>
