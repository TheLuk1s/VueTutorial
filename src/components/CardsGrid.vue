<template>
  <div class="cardsGrid">
    <Card
      v-for="person in people"
      :key="person.uuid"
      class="card"
      :name="person.name"
      :link="person.link"
      :tweets="person.tweets"
      :following="person.following"
      :followers="person.followers"
    />

    <!-- Bind solution -->
    <Card v-for="person in people" :key="person.uuid" v-bind="person" />
  </div>
</template>

<script>
import Card from "./Card";

export default {
  name: "CardsGrid",

  components: {
    Card,
  },

  data() {
    return {
      people: [
        {
          name: "Vardas1",
          link: "https://www.google.com/",
          tweets: 10,
          following: 4,
          followers: 2,
        },
        {
          name: "Vardas2",
          link: "https://www.google.com/",
          tweets: 15,
          following: 300,
          followers: 64,
        },
        {
          name: "Vardas3",
          link: "https://www.google.com/",
          tweets: 3,
          following: 8000,
          followers: 342,
        },
        {
          name: "Vardas4",
          link: "https://www.google.com/",
          tweets: 7,
          following: 413,
          followers: 188,
        },
        {
          name: "Vardas5",
          link: "https://www.google.com/",
          tweets: 11,
          following: 458,
        },
      ],
    };
  },
};
</script>

<style scoped lang="scss">
$gap: 12px;

.cardsGrid {
  width: 100%;
  display: flex;
  flex-flow: row wrap;
  gap: $gap;

  .card {
    flex: 0 1 calc(33% - 8px);
  }
}
</style>