<template>
  <div class="carousel">
    <div v-for="(image, index) in images" :key="index" class="carousel-item">
      <img :src="image.url" :alt="image.alt" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Carousel',
  data() {
    return {
      images: [
        { url: 'https://p-id.ipricegroup.com/trends-article/alasan-mengapa-asics-adalah-sepatu-untuk-sang-pelari-sejati-medium.jpg', alt: 'Joyride Sneakers' },
        { url: 'data:image/jpeg;base64,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', alt: 'Image 2' },
        { url: 'https://www.bing.com/th/id/OIP.kr5-j0IqRoIHupOgGGUrBAHaD4?w=313&h=184&c=7&r=0&o=5&dpr=1.5&pid=1.7', alt: 'Image 3' }
      ]
    }
  }
}
</script>

<style>
.carousel {
  display: flex;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  padding: 10px ; /* Padding atas dan bawah */
  margin-bottom: 20px; /* Jarak bawah */
}

.carousel-item {
  scroll-snap-align: start;
  flex: none;
  width: 100%; /* Lebar item carousel */
  margin-right: 10px; /* Jarak antar item */
  border-radius: 8px; /* Sudut bulat */
  overflow: hidden; /* Mengatasi overflow */
}

.carousel-item img {
  width: 100%; /* Lebar gambar */
  max-height: 500px; /* Tinggi maksimum gambar */
  object-fit: cover; /* Memastikan gambar mengisi seluruh area */
  border-radius: 8px; /* Memberikan sudut bulat pada gambar */
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1); /* Efek bayangan untuk tampilan yang lebih menarik */
  transition: transform 0.3s ease; /* Efek transisi saat gambar dihover */
}

.carousel-item:hover img {
  transform: scale(1.05); /* Memperbesar gambar saat dihover */
}

@media (max-width: 768px) {
  .carousel-item {
    width: 90%; /* Lebar item carousel untuk tampilan mobile */
  }
}
</style>
