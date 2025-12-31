<script lang="ts">
export default {
  name: 'CollectionItem',
  props: {
    title: {
      type: String,
      required: true,
    },
    price: {
      type: String,
      required: true,
    },
    imageSrc: {
      type: String,
      required: true,
    },
  },
};
</script>

<template>
  <div class="collection-item">
    <img
      class="collection-item__image"
      :src="imageSrc"
      :alt="title + ` image`"
    />
    <div class="card-content">
      <h4>{{ title }}</h4>
      <div class="card-bottom">
        <span class="price">{{ price }}</span>
        <button>Add to Cart</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
* {
  box-sizing: border-box;
}
.collection-item {
  --collection-item-background: #c2b6a5;
  --card-content-background: #e4d9c7af;
  background-color: var(--collection-item-background);
  border: 2px solid var(--collection-item-background);
  border-radius: var(--border-radius);
  aspect-ratio: 1/1;
  min-width: 200px;
  max-width: 400px;

  padding: 0.7rem;
  display: grid;
  flex: 1;

  cursor: pointer;
  transition: 0.25s;
}
.collection-item:hover {
  transform: scale(1.1);
  border: 2px solid #ffffffc3;
  /* border-color: var(--card-content-background); */
}

img {
  background-color: rgb(36, 36, 36);
  display: block;
  width: 100%;
  /* height: 100%; */
  aspect-ratio: 1/0.667;
  border-radius: calc(var(--border-radius) - 2px);
  object-fit: cover;
  margin: 0;
}
.card-content {
  background-color: var(--card-content-background);
  margin-top: 0.5em;
  padding: 10px;
  border-radius: calc(var(--border-radius) - 2px);
  min-height: 120px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
h4 {
  margin: 0;
  text-align: start;
  border-radius: 8px;
}
.card-bottom {
  display: flex;
  justify-content: space-between;
}
span {
  text-align: start;
  float: start;
  padding: 0.6em 0;
  border-radius: 8px;
  margin-inline: auto;
}
button {
  /* background-color: rgb(255, 136, 89);
  color: black; */
  border-radius: 1000px;
  white-space: nowrap;
  transition: 0.25s;
  border: none;
}
button:hover {
  transform: scale(1.05);
}
button:active {
  transform: scale(1);
}
</style>
