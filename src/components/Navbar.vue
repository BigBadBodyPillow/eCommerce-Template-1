<template>
  <nav className="navbar">
    <div class="logo">Logo</div>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Services</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
    <!-- <div class="search" type="text">Search</div> -->
    <input class="search" type="text" placeholder="Search" />
    <div class="button-group">
      <!-- <button>O</button> -->
      <button class="cart" aria-label="Cart button"></button>
      <button class="settings" aria-label="settings button"></button>
    </div>
  </nav>
</template>

<style scoped>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  /* font-family: 'Space Grotesk'; */
}
.navbar {
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 2rem;
  /* background-color: #333; */
}
.logo {
  /* margin-left: 20px; */
  float: left;
  font-size: 3rem;
  font-weight: bold;
  transition: 0.25s;
  cursor: pointer;
  user-select: none;
}
.logo:active {
  transform: scale(0.9);
}
nav,
ul {
  height: 100%;
}
ul {
  margin-left: auto;
  list-style: none;
}
li {
  display: inline;
  line-height: 80px;
  margin: 0 5px;
}
a {
  color: inherit;
  display: inline-block;
  font-weight: 500;

  padding-inline: 1rem;
  text-transform: uppercase;
  transition: 0.25s;
}
.search {
  margin-inline: auto;
  float: right;
  margin-right: 20px;
  border: 2px solid;
  border-radius: 1000px;
  padding-inline: 1rem;
  height: 2.5rem;
  /* background-color: transparent; */
  background-color: white;
  color: inherit;
  font-weight: 500;
}
.search::placeholder {
  color: inherit;
  font-weight: 500;
}
.button-group {
  float: right;
  display: flex;
  gap: 10px;
}
button {
  width: 2.5rem;
  height: 2.5rem;
  border-radius: 50%;
  border: 2px solid;
  cursor: pointer;
  /* line-height: 2.5rem; */
  /* background-color: var(--colour);
  color: rgb(11, 11, 11); */
  background-color: white;
  color: black;
  /* border: none; */

  transition: 0.25s;
}
a:hover,
button:hover {
  transform: scale(1.1);
}
a:active,
button:active {
  transform: scale(1);
}
.settings {
  background-image: url('../assets/icons/settings2-svgrepo-com.svg');
  background-repeat: no-repeat;
  background-position: center;
  background-size: 40%;
}
.cart {
  background-image: url('../assets/icons/cart-1-svgrepo-com.svg');
  background-repeat: no-repeat;
  background-position: center;
  background-size: 60%;
}
/* @media (prefers-color-scheme: light) {
  button {
    background-color: white;
    color: black;
  } 
}*/

/* Disable animation when reduced motion is preferred */
@media (prefers-reduced-motion: reduce) {
  .rainbow-line {
    animation: none;
  }
}
</style>
