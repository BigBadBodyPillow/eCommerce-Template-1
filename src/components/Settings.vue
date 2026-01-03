<template>
  <div class="settings" popover id="settings-popover">
    <h3>Settings</h3>
    <!-- <ul>
      <li><a href="#">settings item 1</a></li>
      <li><a href="#">settings item 2</a></li>
      <li><a href="#">settings item 3</a></li>
      <li><a href="#">settings item 4</a></li>
      <li><a href="#">settings item 5</a></li>
      <li><a href="#">settings item 6</a></li>
      <li><a href="#">settings item 7</a></li>
      <li><a href="#">settings item 8</a></li>
      <li><a href="#">settings item 9</a></li>
      <li><a href="#">settings item 10</a></li>
    </ul> -->

    <!-- <hr /> -->
    <button>Option 1</button>
  </div>
</template>

<style scoped>
.settings {
  margin: 0; /* Prevents center/center */
  margin-left: auto;
  margin-right: 2rem;
  margin-top: 72px;
  border-radius: var(--border-radius);
  padding: 1rem;
  border: 0;
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
  overflow-y: scroll;
}
li {
  padding: 1rem;
  background-color: #c2b6a5;
  border-bottom: 1px solid var(--background-colour_alt);
  transition: all 150ms;
  border-radius: var(--border-radius);
}
li:not(:first-child) {
  margin-top: 0.5rem;
}
li:hover {
  background-color: black;
  color: var(--background-colour_alt);
  cursor: pointer;
}
li a {
  display: block;
  color: var(--colour);
}
li:hover a {
  color: white;
}
.settings {
  background-color: var(--background-colour_alt);
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
.settings {
  --hidden: 100vw;
  --visible: 0;
  min-width: 200px;
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
