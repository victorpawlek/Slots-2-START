<template>
  <div class="container mt-5" id="app">
    <Catogram :cats="cats">
      <template #boss="{item}">
        <h5>{{ item.name }}</h5>
        <img :src="item.image" width="200" alt="" />
      </template>
      <template #employees="{item}">
        
          <h5>{{ item.name }}</h5>
          <img :src="item.image" width="200" alt="" />
          <p class="mt-2 fw-bold">Job role: {{ item.role }}</p>
        
      </template>
    </Catogram>
  </div>
</template>

<script>
import cats from '@/assets/cats.json';

import Catogram from '@/components/Catogram.vue';

export default {
  name: 'App',
  components: {
    Catogram,
  },
  data() {
    return {
      cats: cats
      // [
      //   { name: 'Jermy', role: 'Boss', img: 'images/jermy.jpg' },
      //   { name: 'Franz', role: 'Sales', img: 'images/franz.jpg' },
      //   { name: 'Pizz', role: 'Research', img: 'images/pizz.jpg' },
      //   { name: 'Stella', role: 'Customer Support', img: 'images/stella.jpg' },
      // ],
    };
  },
};
</script>
