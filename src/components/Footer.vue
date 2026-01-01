<template>
  <div class="main">
    <div class="left-side">
      <div class="logo">Logo</div>
      <div class="tagline">Your trusted eCommerce partner</div>
      <div class="social-media">
        <a href="#" aria-label="Facebook"
          ><img src="../assets/icons/facebook-icon.svg" alt="Facebook"
        /></a>
        <a href="#" aria-label="LinkedIn"
          ><img src="../assets/icons/linkedin.svg" alt="Facebook"
        /></a>
        <a href="#" aria-label="Instagram"
          ><img src="../assets/icons/instagram-icon.svg" alt="Facebook"
        /></a>
        <a href="#" aria-label="X (Formerly Twitter)"
          ><img src="../assets/icons/x_dark.svg" alt="Facebook"
        /></a>
      </div>
    </div>
    <div class="right-side">
      <nav>
        <h3>Navigation</h3>
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">About</a></li>
          <li><a href="#">Services</a></li>
          <li><a href="#">Contact</a></li>
          <li><a href="#">Cart</a></li>
          <li><a href="#">Settings</a></li>
        </ul>
      </nav>
      <div class="helpful-links">
        <h3>Helpful Links</h3>
        <ul>
          <li><a href="#">FAQ</a></li>
          <li><a href="#">Customer Service</a></li>
          <li><a href="#">Shipping Info</a></li>
          <li><a href="#">Returns & Exchanges</a></li>
          <li><a href="#">Privacy Policy</a></li>
        </ul>
      </div>
    </div>
  </div>
  <div class="bottom">
    <p>&copy; 2026 Company. All rights reserved.</p>
  </div>
</template>

<style scoped>
* {
  padding: 0;
  margin: 0;
}
ul {
  list-style: none;
  text-align: start;
}
h3 {
  text-align: start;
  color: white;
}
a {
  color: #ffcc9f;
  text-decoration: none;
}
img {
  width: 32px;
  height: 32px;
  /* aspect-ratio: 1/1; */
}
.main {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 5rem;
  background-color: #222;
  margin-top: 10rem;
}
@media (max-width: 868px) {
  .main {
    padding: 3rem;
  }
}
@media (max-width: 868px) {
  .main {
    padding: 3rem;
  }
}
@media (max-width: 770px) {
  .main {
    padding: 3rem 1rem;
  }
}
.right-side {
  display: flex;

  justify-content: space-between;
  gap: 5rem;
}
@media (max-width: 700px) {
  .main {
    flex-direction: column;
  }
  .right-side {
    margin-top: 3rem;
    gap: 5rem;
    justify-content: center;
  }
}
.bottom {
  background-color: #3a3a3a;
  color: #fff;
  text-align: center;
  padding: 1rem 0;
}
.logo {
  /* float: left; */
  color: white;
  font-size: 3rem;
  font-weight: bold;
  cursor: pointer;
  user-select: none;
  /* line-height: var(--height); */
  /* transition: 0.25s; */
}
.tagline {
  margin-top: 0.5rem;
  font-size: 1.2rem;
  color: #ccc;
}
.social-media {
  margin-top: 1rem;
}
.social-media a {
  display: inline-block;
  margin: 0 1rem;
  width: 32px;
  height: 32px;
  padding: 0.25rem;
}
</style>
