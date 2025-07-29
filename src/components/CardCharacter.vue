<template>
  <div class="character">
    <img :src="character.image" :alt="character.name" />
    <div class="character__info">
      <h3 class="character__info">{{ character.name }}</h3>

      <div class="status">
        <span
          :class="{
            alive: character.status === 'Alive',
            dead: character.status === 'Dead',
            default:
              character.status !== 'Alive' && character.status !== 'Dead',
          }"
        ></span>
        <span>{{ character.status }} - {{ character.species }}</span>
      </div>
      <div class="origin">
        <span> Origin: {{ character.origin.name }} </span>
      </div>
      <div class="location">
        Location:
        {{ character.location.name }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["character"],
};
</script>

<style scoped lang="scss">
.character {
  display: flex;
  flex-direction: column;
  border: 1px solid #ccc;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
  background-color: #fff;
  transition: transform 0.2s;
  cursor: pointer;

  &:hover {
    transform: translateY(-4px);
  }

  img {
    width: 100%;
    height: auto;
    object-fit: cover;
  }

  .character__info {
    padding: 1rem;

    h3 {
      margin: 0 0 0.5rem;
      font-size: 1.2rem;
    }

    .status {
      display: flex;
      align-items: center;
      margin-bottom: 0.5rem;

      span:first-child {
        width: 10px;
        height: 10px;
        border-radius: 50%;
        display: inline-block;
        margin-right: 8px;
      }

      .alive {
        background-color: #28a745;
      }

      .dead {
        background-color: #dc3545;
      }

      .default {
        background-color: #6c757d;
      }
    }

    .origin,
    .location {
      font-size: 0.9rem;
      color: #333;
      margin-top: 4px;
    }
  }
}
</style>
