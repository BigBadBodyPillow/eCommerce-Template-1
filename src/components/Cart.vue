<template>
  <div class="cart" popover id="cart-popover">
    <ul>
      <li><a href="#">cart item 1</a></li>
      <li><a href="#">cart item 2</a></li>
      <li><a href="#">cart item 3</a></li>
      <li><a href="#">cart item 4</a></li>
      <li><a href="#">cart item 5</a></li>
      <li><a href="#">cart item 6</a></li>
      <li><a href="#">cart item 7</a></li>
      <li><a href="#">cart item 8</a></li>
      <li><a href="#">cart item 9</a></li>
      <li><a href="#">cart item 10</a></li>
    </ul>

    <hr />
    <button>Checkout</button>
  </div>
</template>

<style scoped>
.cart {
  --green-dark: black;
  --green-med: #c2b6a5;
  --background-colour: #f6f7f1;

  margin: 0; /* Prevents center/center */
  margin-left: auto;
  margin-right: 2rem;
  margin-top: 72px;
  border-radius: var(--border-radius);
  padding: 1rem;
  border: 0;
}
ul {
  margin: 0;
  padding: 0;
  min-width: 200px;
  list-style: none;
  max-height: 650px;
  overflow-y: scroll;
}
li {
  padding: 1rem;
  background-color: var(--green-med);
  border-bottom: 1px solid var(--background-colour);
  transition: all 150ms;
  border-radius: var(--border-radius);
}
li:not(:first-child) {
  margin-top: 0.5rem;
}
li:hover {
  background-color: var(--green-dark);
  color: var(--background-colour);
  cursor: pointer;
}
li a {
  display: block;
  color: var(--colour);
}
li:hover a {
  color: white;
}
.cart {
  background-color: var(--background-colour);
  box-shadow: 2px 0 8px black;
}
hr {
  border-radius: 200px;
}
button {
  width: 100%;
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
