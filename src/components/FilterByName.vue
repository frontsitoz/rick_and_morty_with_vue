<template>
  <div class="search">
    <input
      type="text"
      placeholder="Search by name"
      v-model="name"
      @keyup="filter"
    />
  </div>
</template>

<script>
import { ref } from "vue";
import { useStore } from "vuex";

export default {
  setup() {
    const store = useStore();
    const name = ref("");

    const filter = () => {
      store.dispatch("filterByName", name.value);
    };

    return {
      name,
      filter,
    };
  },
};
</script>

<style lang="scss">
.search {
  width: 400px;
  margin: 3rem auto 0;

  input {
    height: 53px;
    width: 400px;
    border: none;
    border-radius: 10px;
    padding: 0 1rem;
    font-size: 16px;
    outline: none;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
  }
}
</style>
