<script setup lang="ts">
import RainbowLine from './components/RainbowLine.vue';
import Main from './components/Main.vue';
import Navbar from './components/Navbar.vue';
import Hero from './components/Hero.vue';
import Collection from './components/Collection/Collection.vue';
import Footer from './components/Footer.vue';
</script>

<template>
  <RainbowLine />
  <Main>
    <Navbar />
    <Hero />
    <Collection />
  </Main>
  <Footer />
</template>
