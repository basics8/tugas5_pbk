<template>
    <div class="carousel">
      <div v-for="(image, index) in images" :key="index" class="carousel-item" @click="openModal(image.url)">
        <img :src="image.url" :alt="image.alt" class="carousel-image" />
      </div>
      <div v-if="modalOpen" class="modal" @click="closeModal">
        <img :src="modalImageUrl" alt="Full-size Image" class="modal-image" />
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Carousel',
    data() {
      return {
        images: [
          { url: 'https://i.pinimg.com/originals/3e/dd/8a/3edd8a2307e925872912bad8efdec7d8.jpg' },
          { url: 'https://kpopping.com/documents/1a/0/2048/EZzI6QfU0AE8MkE.jpeg?v=9d1b6' },
          { url: 'https://kpopping.com/documents/c0/1/4096/EaODd1tU8AAgCku.jpeg?v=491c7' }
        ],
        modalOpen: false,
        modalImageUrl: ''
      }
    },
    methods: {
      openModal(url) {
        this.modalOpen = true;
        this.modalImageUrl = url;
      },
      closeModal() {
        this.modalOpen = false;
      }
    }
  }
  </script>
  
  <style>
  .carousel {
    display: flex;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
    padding: 10px;
    margin-bottom: 20px;
  }
  
  .carousel-item {
    scroll-snap-align: start;
    flex: none;
    width: 100%;
    margin-right: 10px;
    border-radius: 8px;
    overflow: hidden;
  }
  
  .carousel-image {
    width: 100%; /* Set the width to fill the entire container */
    height: auto; /* Automatically adjust the height to maintain aspect ratio */
    object-fit: cover; /* Cover the entire area of the container */
    border-radius: 8px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease;
  }
  
  .carousel-item:hover .carousel-image {
    transform: scale(1.05);
  }
  
  .modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.8);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .modal-image {
    max-width: 90%;
    max-height: 90%;
    object-fit: contain;
  }
  </style>