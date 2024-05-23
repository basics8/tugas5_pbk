<template>
  <div>
    <Navbar />
    <div class="container mt-4">
      <div class="main-content">
        <Sidebar />
        <div class="content">
          <Carousel />
          <div class="cards-container mt-4">
            <Card
              v-for="product in products"
              :key="product.id"
              :title="product.name"
              :description="product.description"
              :image="product.image"
            />
          </div>
        </div>
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
import Sidebar from './components/Sidebar.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    Carousel,
    Card,
    Footer,
    Sidebar  // Register Sidebar
  },
  data() {
    return {
      products: [
        { id: 1, name: 'TEDDY BEAR (BEAR DOLL) SHORT SLEEVE T-SHIRT BEIGE', description: 'Rp. 899,999 ', image: 'https://acmedelavie.co.id/cdn/shop/files/a63ba3a4296828d686df3ae809328cc1_1080x1080.jpg?v=1696923331' },
        { id: 2, name: 'DIN2LS CREATURE SHORT SLEEVE T-SHIRT CREAM', description: 'Rp. 899,999 ', image: 'https://acmedelavie.co.id/cdn/shop/files/1_7656657a-b564-4927-bd92-ae9a57660911_1080x1080.png?v=1692181326' },
        { id: 3, name: 'BABY FACE MONSTER BABY SHORT SLEEVE T-SHIRT BLACK', description: 'Rp. 899,999 ', image: 'https://acmedelavie.co.id/cdn/shop/files/33df93d6c36391e202c00ed33508d508_1080x1080.jpg?v=1711350339' },
        { id: 4, name: 'ADLV BABY FACE SHORT SLEEVE T-SHIRT BLACK CAP BOY', description: 'Rp. 899,999 ', image: 'https://acmedelavie.co.id/cdn/shop/files/103d4a41d4ed04842e5ac9d77a769609_1080x1080.jpg?v=1698746195' },
        { id: 5, name: 'CREAM FUZZY RABBIT SHORT SLEEVE T-SHIRT CREAM', description: 'Rp. 899,999 ', image: 'https://acmedelavie.co.id/cdn/shop/files/23bb21eec258238d9969dd665f65db70_1080x1080.jpg?v=1692180251' },
        { id: 7, name: 'FUZZY BEAR HOODIE IVORY', description: 'Rp. 1,799,999 ', image: 'https://acmedelavie.co.id/cdn/shop/files/f8d882ea52206a549f8b8fb2ab57b976_1080x1080.jpg?v=1704960193' }
        // Add more products as needed
      ]
    };
  }
};
</script>

<style>
body {
  background-color: rgba(130, 96, 79, 0.825);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.main-content {
  display: flex;
}

.content {
  flex: 1;
}

.container::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('https://stock.adobe.com/id/images/color-papers-geometry-composition-background-with-beige-light-brown-and-dark-brown-tones/358642992');
  background-size: cover;
  background-position: center;
  filter: blur(10px);
  z-index: -1;
}

.cards-container {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  justify-content: center;
}

.card {
  width: 300px;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 10px;
  background-color: #fff;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.card img {
  width: 100%;
  border-radius: 8px;
}
.card h2 {
  font-size: 24px;
  margin-bottom: 10px;
}

.card p {
  font-size: 18px;
  color: #666;
}
</style>