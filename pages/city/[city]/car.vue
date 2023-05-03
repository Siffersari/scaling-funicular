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
      <NuxtErrorBoundary>
        <CarSideBar />

        <NuxtPage />
        <template #error="{ error }">
          <div class="text-center mx-auto flex flex-col">
            <h1 class="text-5xl text-red-600 mb-4">
              Sorry, Something went wrong!
            </h1>
            <code>{{ error }}</code>
            <button
              @click="error.value = null"
              class="text-white bg-blue-400 px-10 py-3 rounded mt-4"
            >
              Go Back
            </button>
          </div>
        </template>
      </NuxtErrorBoundary>
    </div>
  </div>
</template>
