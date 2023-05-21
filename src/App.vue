<template>
  <div id="app">
    <h1 class="shadow-text">{{ title }}</h1>
    <p class="shadow-text">{{ description }}</p>
    <button @click="purchase">{{ buttonText }}</button>
  </div>
</template>

<script>
import backgroundImage from "@/assets/chocolate-fruit.jpg";

export default {
  data() {
    return {
      title: 'For Sale: Chocolate covered fruit baskets',
      description: 'A unique basket of sliced fruit covered in chocolate',
      buttonText: 'Buy Now',
      backgroundImage: backgroundImage
    };
  },
  mounted() {
    document.body.style.backgroundImage = `url(${this.backgroundImage})`;
    document.body.style.backgroundSize = 'cover';
    document.body.style.backgroundRepeat = 'no-repeat';
    document.body.style.backgroundPosition = 'center center';
    document.body.style.backgroundAttachment = 'fixed';
  },
  beforeUnmount() {
    document.body.style.backgroundImage = null;
  },
  methods: {
    purchase: function () {
      alert('You clicked Buy Now! This would typically start the purchase process.')
    },
  },
};
</script>

<style scoped>
body {
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
  color: #f0e9e2;
}

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  padding: 1rem;
  box-sizing: border-box;
  text-align: center;
}

.shadow-text {
  text-shadow: 2px 2px 4px #000000;
}

h1 {
  font-size: 2rem;
  color: #b78c6a;
}

p {
  font-size: 1.2rem;
  color: #e7d4c1;
  margin: 2rem 0;
}

button {
  padding: 1rem 2rem;
  font-size: 1.2rem;
  color: #f0e9e2;
  background-color: #b78c6a;
  border: none;
  border-radius: 0.5rem;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #a07151;
}

@media (min-width: 768px) {
  h1 {
    font-size: 3rem;
  }

  p {
    font-size: 1.5rem;
  }

  button {
    font-size: 1.5rem;
  }
}
</style>
