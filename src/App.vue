<template>
  <div id="app">
    <h1 class="shadow-text">{{ title }}</h1>
    <div class="shadow-text" v-html="description"></div>
    <button @click="purchase">{{ buttonText }}</button>
  </div>
</template>

<script>
import backgroundImage from "@/assets/chocolate-fruit.jpg";

export default {
  data() {
    return {
      title: 'Treat Your Senses: Our Premium Chocolate-Drizzled Fruit Baskets',
      description: '<p>Unveiling the epitome of luxury and elegance with our Premium Chocolate-Drizzled Fruit Baskets. Specially curated for discerning palates, each basket showcases a rich assortment of the season\'s finest fruits, expertly hand-dipped in velvety, indulgent chocolate. The harmonic balance between the sweetness of the fruits and the creaminess of the chocolate creates an exquisite blend of flavors that indulges your senses and elevates your experience.</p><p>Our focus on quality is relentless and uncompromising. We hand-select every piece of fruit to ensure optimal ripeness and flavor. Our chocolatiers meticulously drizzle each slice with gourmet chocolate, creating a beautiful and tantalizing presentation. Whether it\'s a gift or a personal indulgence, our Chocolate-Drizzled Fruit Baskets promise an unforgettable experience of taste and refinement, embodying the very essence of luxury.</p>',
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
  background: rgba(0, 0, 0, 0.7);
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
  background: rgba(0, 0, 0, 0.3);
  border-radius: 1rem;
  backdrop-filter: blur(1px);
}



.shadow-text {
  text-shadow: 2px 2px 4px #000000;
}

h1 {
  font-size: 2rem;
  color: #b78c6a;
}

div.shadow-text {
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

  div.shadow-text {
    font-size: 1.5rem;
  }

  button {
    font-size: 1.5rem;
  }
}
</style>



