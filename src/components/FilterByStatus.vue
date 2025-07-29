<template>
  <div class="filter">
    <div class="item" @click="filterByStatus('')">All</div>
    <div class="item" @click="filterByStatus('Alive')">Alive</div>
    <div class="item" @click="filterByStatus('Dead')">Dead</div>
    <div class="item" @click="filterByStatus('unknown')">Unknown</div>
  </div>
</template>

<script>
import { useStore } from "vuex";

export default {
  setup() {
    const store = useStore();
    const filterByStatus = (status) => {
      store.dispatch("filterCharactersByStatus", status);
    };
    return {
      filterByStatus,
    };
  },
};
</script>

<style lang="scss" scoped>
.filter {
  width: 400px;
  margin: 0 auto;
  display: flex;
  grid-template-columns: repeat(4, 1fr);
  border-radius: 10px;
  overflow: hidden;
}
.item {
  flex: 1;
  padding: 10px;
  text-align: center;
  cursor: pointer;
  background-color: #f0f0f0;
  transition: background-color 0.3s;

  &:hover {
    background-color: #dcdcdc;
  }
}
</style>
