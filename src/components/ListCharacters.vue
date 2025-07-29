<template>
  <section>
    <div class="characters">
      <div
        class="characters__item"
        v-for="character in characters"
        :key="character.id"
      >
        <CardCharacter :character="character" />
      </div>
    </div>
  </section>
</template>

<script>
import { computed, onMounted } from "vue";
import { useStore } from "vuex";
import CardCharacter from "./CardCharacter.vue";
export default {
  components: {
    CardCharacter,
  },
  setup() {
    const store = useStore();
    const characters = computed(() => {
      return store.state.charactersFilter;
    });

    onMounted(() => {
      store.dispatch("getCharacters");
    });

    return {
      characters,
    };
  },
};
</script>

<style lang="scss" scoped>
.characters {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
  padding: 2rem;
}
</style>
