<template>
  <div class="character">
    <img :src="character.image" :alt="character.name" />
    <div class="character__info">
      <h2>{{ character.name }}</h2>
      <div class="status">
        <span
          class="dot"
          :style="{
            backgroundColor:
              character.status === 'Alive'
                ? 'green'
                : character.status === 'Dead'
                ? 'red'
                : 'gray',
          }"
        ></span>

        <span>{{ character.status }} - {{ character.species }}</span>
      </div>
      <p><strong>Origin:</strong> {{ character.origin.name }}</p>
      <p><strong>Location:</strong> {{ character.location.name }}</p>
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
  width: 280px;
  height: 460px; // altura uniforme para todos
  display: flex;
  flex-direction: column;
  background-color: #fff;
  border: 1px solid #e5e7eb; // gris claro tipo Tailwind
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
  transition: transform 0.2s ease-in-out;

  &:hover {
    transform: translateY(-4px);
  }

  img {
    width: 100%;
    height: 250px;
    object-fit: cover;
  }

  .character__info {
    flex: 1;
    padding: 0.75rem 1rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 0.4rem;

    h2 {
      font-size: 1.1rem;
      font-weight: 600;
      margin: 0;
    }

    p {
      margin: 0;
      font-size: 0.9rem;
      line-height: 1.3;
    }

    .status {
      display: flex;
      align-items: center;
      gap: 0.4rem;
      font-size: 0.9rem;

      .dot {
        width: 10px;
        height: 10px;
        border-radius: 50%;
        background-color: red; // verde
      }
    }
  }
}
</style>
