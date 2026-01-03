<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue';

const showMenu = ref<boolean>(
  typeof window !== 'undefined' ? window.innerWidth < 850 : false
);
const manualPreference = ref<boolean | null>(null);

function resizeHandler() {
  if (typeof window === 'undefined') return;
  if (window.innerWidth >= 850) {
    showMenu.value = false;
    return;
  }
  if (manualPreference.value === false) {
    showMenu.value = false;
  } else if (manualPreference.value === true) {
    showMenu.value = true;
  } else {
    showMenu.value = true;
  }
}

onMounted(() => {
  if (typeof window === 'undefined') return;
  window.addEventListener('resize', resizeHandler);
  if (window.innerWidth >= 850) {
    showMenu.value = false;
  } else {
    showMenu.value = manualPreference.value === false ? false : true;
  }
});

onBeforeUnmount(() => {
  if (typeof window === 'undefined') return;
  window.removeEventListener('resize', resizeHandler);
});

function toggleMenu() {
  if (typeof window === 'undefined') return;
  if (window.innerWidth < 850) {
    showMenu.value = !showMenu.value;
    manualPreference.value = showMenu.value;
  }
}
</script>

<template>
  <header :class="['navbar', { open: showMenu }]">
    <div
      :class="['logo', { open: showMenu }]"
      @click="toggleMenu"
      @keydown.enter="toggleMenu"
      role="button"
      tabindex="0"
    >
      Logo
      <!-- {{ asdasdasd }} -->
    </div>
    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>
    <!-- <div class="search" type="text">Search</div> -->
    <input class="search" type="text" placeholder="Search" />
    <div class="button-group">
      <!-- <button>O</button> -->
      <button
        class="cart"
        aria-label="Cart button"
        popovertarget="cart-popover"
      ></button>
      <button
        class="settings"
        aria-label="settings button"
        popovertarget="settings-popover"
      ></button>
    </div>
  </header>

  <nav class="mobile-menu" v-if="showMenu" aria-hidden="false">
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Services</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
</template>

<style scoped>
* {
  --height: 72px;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  /* font-family: 'Space Grotesk'; */
}
.navbar {
  height: var(--height);
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 2rem;
  margin-top: 8px;
  max-width: 1800px;
  margin-inline: auto;
  /* background-color: #333; */
}
.logo {
  /* margin-left: 20px; */
  float: left;
  font-size: 3rem;
  font-weight: bold;
  cursor: pointer;
  user-select: none;
  /* line-height: var(--height); */
  /* transition: 0.25s; */
}
/* .logo:active {
  transform: scale(0.9);
} */
/* nav,
ul {
  height: 100%;
} */
header nav {
  margin-left: auto;
  list-style: none;
}
li {
  display: inline;
  line-height: var(--height);
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
  padding-inline: 0.9rem;
  height: 2.5rem;
  background-color: transparent;
  /* background-color: white; */
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
  /* background-color: transparent; */
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

@media (min-width: 1200px) {
  nav {
    /* margin-left: calc(100% - 50%); */
    transform: translate(30%);
  }
}

@media (max-width: 980px) {
  li {
    margin: 0;
  }
  a {
    padding-inline: 0.5rem;
  }
}
@media (max-width: 880px) {
  a {
    padding-inline: 0.3rem;
  }
}

@media (max-width: 852px) {
  /* disable default nav */
  * {
    --menu-background-colour: rgb(17, 14, 14);
  }
  header nav {
    display: none;
  }

  .mobile-menu {
    background-color: var(--menu-background-colour);
    color: white;
    /* 100% - 2 rem margin on either side*/
    width: calc(100% - 4rem);
    margin-inline: 2rem;
    border-radius: 20px;
  }

  .mobile-menu ul {
    display: flex;
    flex-direction: column;
    align-items: start;
    position: relative;
  }

  .mobile-menu li {
    /* display: inline; */
    padding: 0.8rem 0;
    /* margin-left: 2rem; */
    line-height: 1.4;
    width: 100%;
    /* text-align: left; */
  }
  .mobile-menu a {
    width: 100%;
    padding: 0;
  }

  .search {
    width: 100%;
    margin-left: 20px;
    min-width: 41px; /* almost a perfect circle but its hard to notice and the s is still vsisible so i think its fine*/
  }
}

@media (min-width: 390px) {
  .logo {
    padding: 0 1rem;
  }
  .logo.open {
    position: relative;
    background-color: var(--menu-background-colour);
    border-radius: 20px 20px 0 0;
    color: white;
  }

  .logo.open:after,
  .logo.open:before {
    content: '';
    position: absolute;
    height: 20px;
    width: 20px;
    bottom: 0;
  }
  .logo.open:after {
    height: 21px;
    width: 21px;
    right: -21px;
    border-radius: 0 0 0 20px;
    background-color: var(--background-colour);
  }
  .logo.open:before {
    right: -20px;
    background-color: var(--menu-background-colour);
  }
  .mobile-menu {
    border-radius: 0 20px 20px 20px;
  }
}
/* Disable animation when reduced motion is preferred */
@media (prefers-reduced-motion: reduce) {
  .rainbow-line {
    animation: none;
  }
}
</style>
