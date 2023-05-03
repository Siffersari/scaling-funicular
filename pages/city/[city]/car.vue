<script setup>
const route = useRoute();

useHead({
  title: `${
    route.params.make ? totTitleCase(route.params.make) : "Cars"
  } in ${totTitleCase(route.params.city)}`,
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
    <div class="mt-32 flex">
      <CarSideBar />

      <NuxtPage />
    </div>
  </div>
</template>
