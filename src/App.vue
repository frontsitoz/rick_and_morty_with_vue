<template>
  <div>
    <h1 style="text-align: center">Rick and Morty</h1>
    <ListCharacters />
  </div>
</template>

<script>
import ListCharacters from "@/components/ListCharacters.vue";

export default {
  name: "App",
  components: {
    ListCharacters,
  },
};
</script>

<style lang="scss">
body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  margin: 0;
  background-color: #f4f4f4;
}

h1 {
  font-size: 2rem;
  margin: 2rem 0;
}
</style>
