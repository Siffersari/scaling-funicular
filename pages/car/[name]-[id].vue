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

if (!car.value) {
  throw createError({
    statusCode: 404,
    message: `Car with ID of ${route.params.id} was not found`,
  });
}

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
