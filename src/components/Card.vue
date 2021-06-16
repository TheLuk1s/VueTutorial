<template>
  <div class="card">
    <!-- Image wrapper -->
    <div class="card-image--wrapper">
      <img class="card-image" src="https://picsum.photos/200" />
    </div>

    <!-- Name wrapper -->
    <div class="card-name--wrapper">
      <a :href="link">{{ name }}</a>
    </div>

    <!-- Popular wrapper -->
    <div v-if="followers > 1000" class="card-popular--wrapper">
      <!-- Badge -->
      <span :class="{ red: isRed }">Popular *</span>
    </div>

    <!-- Stats wrapper -->
    <div class="card-numbers--wrapper">
      <div class="row">
        <div class="flex-item">Tweets</div>
        <div class="flex-item">Following</div>
        <div class="flex-item">Followers</div>
      </div>
      <div class="row">
        <div class="flex-item">{{ tweets }}</div>
        <div class="flex-item">{{ following }}</div>
        <div class="flex-item">{{ followers }}</div>
      </div>
    </div>

    <!-- Remove button -->
    <div class="removeButton--wrapper">
      <button>Remove</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    name: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      required: true,
    },
    tweets: {
      type: Number,
      default: 0,
    },
    following: {
      type: Number,
      default: 0,
    },
    followers: {
      type: Number,
      default: 0,
    },
  },
  computed: {
    isRed() {
      return this.followers > 1000;
    },
  },
};
</script>

<style scoped lang="scss">
.card {
  width: 100%;
  background-color: #595FFF;
  display: block;
  border: 1px solid #000;
}
.red {
  color: red;
}

.removeButton--wrapper {
  margin-bottom: 20px;
}

.card-image--wrapper {
  padding: 20px 20px 10px 20px;
  img {
    width: 100%;
    border: 1px solid #000;
  }
}

.card-name--wrapper {
  a {
    text-transform: uppercase;
    text-decoration: none;
    color: #fff;
  }
}

.card-numbers--wrapper {
  margin-top: 15px;
  margin-bottom: 20px;
}

.card-popular--wrapper {
  margin-top: 5px;
}

.row {
  display: flex;
  flex-flow: row wrap;

  .flex-item {
    color: #000;
    flex: 0 1 33%;
  }
}
</style>