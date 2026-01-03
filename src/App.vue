<script setup lang="ts">
import RainbowLine from './components/RainbowLine.vue';
import Main from './components/Main.vue';
import Navbar from './components/Navbar.vue';
import Cart from './components/Cart.vue';
import Hero from './components/Hero.vue';
import Collection from './components/Collection/Collection.vue';
import Footer from './components/Footer.vue';
</script>

<template>
  <RainbowLine />
  <Main>
    <Navbar />
    <Cart />
    <Hero />
    <Collection />
  </Main>
  <Footer />
</template>
