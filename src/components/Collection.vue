<template>
  <div class="collection">
    <h2>Collection</h2>
    <div class="collection-items">
      <div>Item 1</div>
      <div>Item 2</div>
      <div>Item 3</div>
      <div>Item 4</div>
      <div>Item 5</div>
      <div>Item 6</div>
      <div>Item 7</div>
      <div>Item 8</div>
      <div>Item 9</div>
      <div>Item 10</div>
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
.collection-items {
  margin: 1rem 2rem;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem;
}
.collection-items div {
  background-color: #c2b6a5;
  border-radius: var(--border-radius);
  aspect-ratio: 1/1;
  /* width: 300px; */
  /* width: 100%; */
  min-width: 200px;
  max-width: 400px;
  display: grid;
  place-content: center;
  flex: 1;

  cursor: pointer;
  transition: 0.25s;
}
.collection-items div:hover {
  transform: scale(1.1);
}
@media (max-width: 1000px) {
  .collection-items {
    grid-template-columns: repeat(3, 1fr);
    /* gap: 2rem; */
  }
}
@media (max-width: 730px) {
  .collection-items {
    grid-template-columns: repeat(2, 1fr);
    /* gap: 2rem; */
  }
}
@media (max-width: 600px) {
  .collection-items {
    gap: 1rem;
  }
}
@media (max-width: 475px) {
  .collection-items {
    grid-template-columns: repeat(1, 1fr);
    gap: 2rem;
  }
}
/* @media (max-width: 1200px) {
  .collection-items {
    gap: 1rem;
  }
}
@media (max-width: 980px) {
  .collection-items div {
    width: 250px;
  }
}
@media (max-width: 840px) {
  .collection-items {
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
  }
  .collection-items div {
    width: 350px;
  }
}
@media (max-width: 800px) {
  .collection-items {
    gap: 1rem;
  }
}
@media (max-width: 760px) {
  .collection-items {
    grid-template-columns: repeat(1, 1fr);
  }
  .collection-items div {
    width: 100%;
  }
} */
</style>
