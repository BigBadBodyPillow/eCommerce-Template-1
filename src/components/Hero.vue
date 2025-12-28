<!-- <script setup lang="ts">
</script> -->

<template>
  <div class="hero">
    <!-- <img src="../assets/bricks/pexels-madebymath-21380.jpg" alt="Hero Image" /> -->
    <div class="gradient"></div>
    <div class="hero-content">
      <h1>Would you buy our Bricks</h1>
      <h3>Discover our premium collection of Bricks</h3>
      <button>Shop Now</button>
    </div>
  </div>
</template>

<style scoped>
.hero {
  --height: 600px;
  position: relative;
  overflow: hidden;
  margin: 1rem 2rem;
  border-radius: 20px;
  height: var(--height);

  background-image: url(../assets/bricks/pexels-madebymath-21380.jpg);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;

  max-width: 1800px;

  /* display: flex;
  flex-direction: column;
  margin: auto; */
}
@media (min-width: 1800px) {
  .hero {
    margin: auto;
  }
}
.gradient {
  position: absolute;
  width: 100%;
  height: 100%;
  background: radial-gradient(
    circle,
    rgba(0, 0, 0, 0.277) 0%,
    rgba(255, 255, 255, 0) 100%
  );
}
.hero-content {
  color: white;
  text-align: center;
  position: relative;
  top: 50%;
  transform: translateY(-50%);
  padding-inline: 1rem;
}
button {
  /* font: inherit; */
  transition: 0.25s;
  border: none;
}
button:hover {
  transform: scale(1.1);
}
button:active {
  transform: scale(1);
}
</style>
