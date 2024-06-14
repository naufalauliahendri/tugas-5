<template>
  <div>
    <Navbar />
    <div class="container mt-4">
      <Carousel />
      <div class="card-container mt-4">
        <Card 
          v-for="product in products" 
          :key="product.id" 
          :title="product.name" 
          :description="product.description" 
          :url="product.url" 
        />
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Carousel from './components/Carousel.vue';
import Card from './components/Card.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    Carousel,
    Card,
    Footer
  },
  data() {
    return {
      products: [
        { 
          id: 1, 
          name: 'Nike Dunk Low Shoes', 
          description: 'Stylish and comfortable, perfect for everyday wear.', 
          url: 'data:image/jpeg;base64,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' 
        },
        { 
          id: 2, 
          name: 'Air Jordan 1 Low Shoes', 
          description: 'Classic style and premium comfort.', 
          url: 'https://pyxis.nymag.com/v1/imgs/d32/403/d1ec9b55c08b070833b0e8d15927748c5c.rsquare.w215.jpg' 
        },
        { 
          id: 3, 
          name: 'Nike Dunk Low Retro', 
          description: 'kkkkkkk', 
          url: 'https://pyxis.nymag.com/v1/imgs/691/0fa/9ca82480ae448cbdef0d35fd35d762c746.rsquare.w215.jpg' 
        },
        { 
          id: 4, 
          name: 'Product 4', 
          description: 'Description of product 4', 
          url: 'https://static.nike.com/a/images/q_auto:eco/t_product_v1/f_auto/dpr_1.5/h_383,c_limit/ed1921be-4eab-45d2-b72b-f23b2db4ad5d/air-max-plus-shoes-dz4jLD.png' 
        },
        { 
          id: 5, 
          name: 'Product 5', 
          description: 'Description of product 5', 
          url: 'https://static.nike.com/a/images/t_prod_ss/w_960,c_limit,f_auto/f89ab2e1-1543-46ad-a09e-a1a753f4b40d/nike-sb-dunk-low-x-futura-laboratories-white-and-geode-teal-hf6061-400-release-date.jpg' 
        },
        { 
          id: 6, 
          name: 'Product 6', 
          description: 'Description of product 5', 
          url: 'https://static.nike.com/a/images/c_limit,w_592,f_auto/t_product_v1/6b902d4d-e794-450c-9c34-c225b0f889bc/v2k-run-shoes-zJV8TV.png' 
        }
      ]
    };
  }
};
</script>

<style>
body {
  background-color: rgb(239, 234, 234);
}

.card-container {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 16px; /* Optional: Adjust the space between cards */
}

.card {
  flex-basis: calc(33.33% - 16px); /* Atur lebar kartu dengan ketiga bagian dari wadah dikurangi jarak antar kartu */
}
</style>
