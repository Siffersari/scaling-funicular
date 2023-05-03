<script setup>
const route = useRoute();

const { totTitleCase } = useUtilities();

useHead({
  title: `${
    route.params.make ? totTitleCase(route.params.make) : "Cars"
  } in ${totTitleCase(route.params.city)}`,
  description: "Find the best value on cars deals in your city",
});

definePageMeta({
  layout: "custom",
});
</script>

<template>
  <div>
    <div class="mt-32 flex">
      <CarSideBar />

      <NuxtPage />
    </div>
  </div>
</template>
