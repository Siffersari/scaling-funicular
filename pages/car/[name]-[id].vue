<script setup>
const route = useRoute();

useHead({
  title: `${totTitleCase(route.params.name)}`,
  description: "Find the best value on cars deals in your city",
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
    <div
      class="mx-auto mt-4 max-w-7xl space-y-4 px-4 xs:px-8 sm:px-10 lg:px-16 pb-16 w-3/4"
    >
      <CarDetailHero />

      <CarDetailAttributes />

      <CarDetailDescription />

      <CarDetailContact />
    </div>
  </div>
</template>
