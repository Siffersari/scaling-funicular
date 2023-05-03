<script setup>
const route = useRoute();

useHead({
  title: `${
    route.params.make ? totTitleCase(route.params.make) : "Cars"
  } in ${totTitleCase(route.params.city)}`,
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
      <div class="mt-32 flex">
        <CarSideBar />

        <NuxtPage />
      </div>
    </div>
  </div>
</template>
