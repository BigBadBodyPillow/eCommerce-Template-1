<script setup lang="ts">
import CollectionItem from './CollectionItem.vue';
// Import images so Vite can resolve them at build/dev time
import brick from '../../assets/collection/bricks_for_home_construction.jpg';
import concrete from '../../assets/collection/concrete-bricks-1708941378-7311212.jpeg';
import brickv2 from '../../assets/collection/1110004-1.jpg';
import brick3 from '../../assets/collection/Clay-Stock-Bricks-3-1.jpeg';
import Corn_satin_scaled from '../../assets/collection/Corn-Satin-scaled.jpg';
import moreBricks from '../../assets/collection/NFP-Stock-Perforated-680x680.jpg';
import bricksAgain from '../../assets/collection/Build-it-Gansbaai-Manufacturing-Concrete-Blocks-1.png';
import lego from '../../assets/collection/landingBricks2.0797f1e722392c9e320a.jpg';
import whiteBricks from '../../assets/collection/TumbledVintageBrick-Alpine-White.png';
import Rusks from '../../assets/collection/ButtermilkRuskSAD-683x1024.jpg';
</script>

<template>
  <div class="collection">
    <h2>Collection</h2>
    <div class="item-collection">
      <CollectionItem
        title="This is a brick"
        price="R199.99"
        :imageSrc="brick"
      />
      <CollectionItem
        title="Another brick but different"
        price="R199.99"
        :imageSrc="concrete"
      />
      <CollectionItem title="third brick" price="R199.99" :imageSrc="brickv2" />
      <CollectionItem
        title="This is the 4th brick"
        price="R199.99"
        :imageSrc="brick3"
      />
      <CollectionItem
        title="Brick again"
        price="R199.99"
        :imageSrc="Corn_satin_scaled"
      />
      <CollectionItem
        title="Also a brick"
        price="R199.99"
        :imageSrc="moreBricks"
      />
      <CollectionItem
        title="Cinder block looking things"
        price="R199.99"
        :imageSrc="bricksAgain"
      />
      <CollectionItem title="Lego bricks" price="R199.99" :imageSrc="lego" />
      <CollectionItem
        title="White bricks in a wall"
        price="R199.99"
        :imageSrc="whiteBricks"
      />
      <CollectionItem title="Rusks" price="R199.99" :imageSrc="Rusks" />
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
