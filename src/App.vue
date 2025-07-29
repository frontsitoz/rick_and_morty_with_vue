<template>
  <div>
    <h1 style="text-align: center">Rick and Morty</h1>
    <FilterByStatus />
    <FilterByName />
    <ListCharacters />
  </div>
</template>

<script>
import ListCharacters from "@/components/ListCharacters.vue";
import FilterByStatus from "./components/FilterByStatus.vue";
import FilterByName from "./components/FilterByName.vue";

export default {
  name: "App",
  components: {
    ListCharacters,
    FilterByStatus,
    FilterByName,
  },
};
</script>

<style lang="scss">
body {
  margin: 0;
  background-color: #f4f4f4; // fondo claro general
  font-family: "Segoe UI", sans-serif;
  color: #222;
}

h1 {
  font-size: 2rem;
  margin: 2rem 0;
}
</style>
