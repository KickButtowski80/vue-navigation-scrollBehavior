<template>
  <div id="app">
    <nav class="nav">
      <router-link :to="{ name: 'Home', hash: '#Hero' }">Home</router-link>
      <router-link :to="{ name: 'Home', hash: '#About-Me' }">About Me</router-link>
      <router-link :to="{ name: 'Home', hash: '#Contact' }">Contact</router-link>
      <router-link :to="{ name: 'Blog' }">Blog</router-link>
    </nav>
    <main>
      <router-view v-slot="{ Component }">
        <transition name="fade" mode="out-in">
          <component :is="Component" />
        </transition>
      </router-view>
    </main>
  </div>
</template>

<script>
import Home from './pages/Home.vue';
import Blog from './pages/Blog.vue';

export default {
  name: 'App',
  components: {
    Home,
    Blog
  }     
};
</script>

<style>
.nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: white;
  display: flex;
  justify-content: center;
  gap: 1rem;
  padding: 1rem;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  z-index: 10;
}
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
</style>