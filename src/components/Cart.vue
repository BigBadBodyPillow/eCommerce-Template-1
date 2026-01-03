<script setup lang="ts">
import { reactive, onMounted, onBeforeUnmount } from 'vue';

type CartItem = {
  ID: string;
  Title: string;
  Price: string;
  imageSrc: string;
  qty?: number;
};

const state = reactive({ bricks: [] as CartItem[] });

function addToCart(brick: CartItem) {
  const found = state.bricks.find((i) => i.ID === brick.ID);
  if (found) {
    found.qty = (found.qty || 1) + 1;
  } else {
    state.bricks.push({ ...brick, qty: 1 });
  }
}

function removeFromCart(id: string) {
  const idx = state.bricks.findIndex((i) => i.ID === id);
  if (idx > -1) state.bricks.splice(idx, 1);
}

function handleCartAdd(e: Event) {
  const ce = e as CustomEvent;
  const payload = ce.detail as CartItem;
  if (payload && payload.ID) addToCart(payload);
}

onMounted(() =>
  window.addEventListener('cart-add', handleCartAdd as EventListener)
);
onBeforeUnmount(() =>
  window.removeEventListener('cart-add', handleCartAdd as EventListener)
);
</script>

<template>
  <div class="cart" popover id="cart-popover">
    <h3>Cart</h3>
    <ul>
      <li v-for="brick in state.bricks" :key="brick.ID">
        <img :src="brick.imageSrc" :alt="brick.Title + ' image'" />
        <div class="info">
          <p class="title">{{ brick.Title }}</p>
          <p class="price">
            {{ brick.Price }}
            <span v-if="brick.qty">( x {{ brick.qty }} )</span>
          </p>
        </div>
        <button @click="removeFromCart(brick.ID)">X</button>
      </li>
    </ul>

    <hr />
    <button class="checkout">Checkout</button>
  </div>
</template>

<style scoped>
.cart {
  margin: 0; /* Prevents center/center */
  margin-left: auto;
  margin-right: 2rem;
  margin-top: 72px;
  border-radius: var(--border-radius);
  padding: 1rem;
  border: 0;
  background-color: var(--background-colour_alt);
  box-shadow: 2px 0 8px black;
}
h3 {
  color: var(--colour);
  margin-top: 0;
}
ul {
  margin: 0;
  padding: 0;
  min-width: 200px;
  list-style: none;
  max-height: 650px;
  /* overflow-y: auto; */
}
li {
  padding: 0.5rem;
  padding-right: 1rem;
  background-color: #c2b6a5;
  border-bottom: 1px solid var(--background-colour_alt);
  transition: all 150ms;
  border-radius: var(--border-radius);

  display: flex;
  gap: 1rem;
  position: relative;
  transition: 0.25s;
}
li:not(:first-child) {
  margin-top: 0.5rem;
}
li:hover {
  background-color: #c2b6a5;
  color: var(--background-colour_alt);
  transform: scale(1.05);
  /* cursor: pointer; */
}
li a {
  display: block;
  color: var(--colour);
}
li:hover a {
  color: white;
}
li button {
  /* height: fit-content; */
  /* margin-block: auto; */
  width: 1.25rem;
  height: 1.25rem;
  position: absolute;
  right: -0.25rem;
  top: -0.25rem;
  border-radius: 50%;
  border: 1px solid;
  cursor: pointer;
  line-height: 0;
  padding: 0;
  background-color: rgb(255, 122, 122);
  color: black;
  font-size: 0.6em;
}
img {
  width: 50px;
  height: 50px;
  object-fit: cover;
  border-radius: var(--border-radius);
}
.info {
  justify-content: space-between;
  display: flex;
  flex-direction: column;
  color: black;
}
p {
  margin: 0;
  text-align: start;
}
hr {
  border-radius: 200px;
}
.checkout {
  width: 100%;
}
button {
  transition: 0.25s;
  border: none;
}
button:hover {
  transform: scale(1.05);
}
button:active {
  transform: scale(1);
}
/* Start offstage, animate onstage, add backdrop */
.cart {
  --hidden: 100vw;
  --visible: 0;
  /* height: auto; */
  translate: var(--hidden);
  &::backdrop {
    background: rgb(0 0 0 / 50%);
  }
  @media (prefers-reduced-motion: no-preference) {
    transition: translate 150ms;
  }
  &:popover-open {
    translate: var(--visible);
    @starting-style {
      translate: var(--hidden);
    }
  }
}
</style>
