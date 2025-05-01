<template>
  <div class="home">
    <section id="Hero" class="section hero">
      <Hero />
    </section>
    <section id="About-Me" class="section about">
      <AboutMe />
    </section>
    <section id="Contact" class="section contact">
      <Contact />
    </section>
  </div>
</template>

<script>
import Hero from '../components/Hero.vue';
import AboutMe from '../components/About-Me.vue';
import Contact from '../components/Contact.vue';
import { useRouter } from 'vue-router';

export default {
  name: 'Home',
  setup() {
    const router = useRouter();
    return { router };
  },

  components: {
    Hero,
    AboutMe,
    Contact
  }
};
</script>

<style scoped>
.section {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
}
.hero {
  background: #ffadad;
}
.about {
  background: #ffd6a5;
}
.contact {
  background: #caffbf;
}
</style>