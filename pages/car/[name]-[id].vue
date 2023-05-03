<script setup>
const route = useRoute();
const { cars } = useCars();

const { totTitleCase } = useUtilities();

useHead({
  title: `${totTitleCase(route.params.name)}`,
  description: "Find the best value on cars deals in your city",
});

const car = computed(() => {
  return cars.find((car) => {
    return car.id === parseInt(route.params.id);
  });
});

definePageMeta({
  layout: "custom",
});
</script>

<template>
  <div v-if="car">
    <CarDetailHero :car="car" />

    <CarDetailAttributes :features="car.features" />

    <CarDetailDescription :description="car.description" />

    <CarDetailContact />
  </div>
</template>
