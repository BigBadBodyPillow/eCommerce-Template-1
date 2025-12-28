<template>
  <div className="navbar">
    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>
  </div>
</template>

<style scoped>
.navbar {
  height: 40px;
  background-color: #333;
}
nav,ul {
  height: 100%;
}
ul {
  margin: 0;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-items: center;
  list-style: none;
}
/* Disable animation when reduced motion is preferred */
@media (prefers-reduced-motion: reduce) {
  .rainbow-line {
    animation: none;
  }
}

</style>
