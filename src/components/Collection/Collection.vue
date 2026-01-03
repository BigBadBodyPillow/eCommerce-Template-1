<script setup lang="ts">
import CollectionItem from './CollectionItem.vue';
import storeData from '../../store_data.json';

//temp due to locally stored store info
const images = import.meta.glob('../../assets/collection/*', {
  eager: true,
}) as Record<string, { default: string }>;

const imageMap: Record<string, string> = Object.fromEntries(
  Object.entries(images).map(([key, mod]) => {
    const parts = key.split('/');
    const filename = parts[parts.length - 1];
    return [filename, mod.default];
  })
);

const bricks = storeData.map((it: any) => ({
  ...it,
  imageSrc: imageMap[it.ImageUrl] || '',
}));

// cart is handled by Cart.vue via window events now
</script>

<template>
  <div class="collection">
    <h2>Collection</h2>
    <div class="item-collection">
      <CollectionItem
        v-for="brick in bricks"
        :key="brick.ID"
        :id="brick.ID"
        :title="brick.Title"
        :price="brick.Price"
        :imageSrc="brick.imageSrc"
      />
      <!-- @add="handleAdd" -->
    </div>
  </div>
</template>

<style scoped>
.collection {
  max-width: 1800px;
  display: flex;
  flex-direction: column;
  margin: auto;
}
.item-collection {
  margin: 1rem 2rem;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem;
}
@media (max-width: 1400px) {
  .item-collection {
    gap: 1rem;
  }
}

@media (max-width: 1000px) {
  .item-collection {
    grid-template-columns: repeat(3, 1fr);
  }
}
@media (max-width: 770px) {
  .item-collection {
    grid-template-columns: repeat(2, 1fr);
  }
}
@media (max-width: 555px) {
  .item-collection {
    grid-template-columns: repeat(1, 1fr);
    gap: 2rem;
  }
  .collection-item {
    max-width: unset;
  }
}
</style>
