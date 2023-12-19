<template>
  <div class="feeling-page">
    <div class="image-container">
      <img :src="currentImage" alt="Feeling Image"/>
    </div>
    <input type="range" min="1" :max="images.length" v-model="sliderValue" class="image-slider"/>
    <button @click="sendSliderData" class="continue-button">Envoyer</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [
        'https://em-content.zobj.net/source/apple/354/grinning-face_1f600.png',
        'https://em-content.zobj.net/source/google/387/grinning-face_1f600.png',
        'https://em-content.zobj.net/source/microsoft/379/grinning-face_1f600.png'
      ], // Remplacer par les chemins de vos images
      sliderValue: 1
    }
  },
  computed: {
    currentImage() {
      return this.images[this.sliderValue - 1]; // Soustrayez 1 car les indices de tableau commencent à 0
    }
  },
  methods: {
    sendSliderData() {
      console.log("Valeur du slider envoyée:", this.sliderValue);
      // Ajoutez ici votre logique d'envoi
    }
  }
};
</script>

<style>
.feeling-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background-color: #fff; /* Couleur de fond (à ajuster selon vos besoins) */
}

.image-container img {
  width: 150px; /* Taille de l'image (à ajuster selon vos besoins) */
  margin-bottom: 30px; /* Espacement entre l'image et le slider */
}

.image-slider {
  -webkit-appearance: none;
  appearance: none;
  width: 70%;
  height: 10px;
  border-radius: 5px;
  background: #d3d3d3;
  outline: none;
  opacity: 0.7;
  -webkit-transition: .2s;
  transition: opacity .2s;
  margin-bottom: 30px; /* Espacement entre le slider et le bouton */
}

.image-slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.image-slider::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #4CAF50;
  cursor: pointer;
}

.continue-button {
  background-color: #007BFF; /* Couleur de fond du bouton */
  border: none;
  border-radius: 20px;
  color: white;
  padding: 15px 30px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  transition-duration: 0.4s;
  cursor: pointer;
}

.continue-button:hover {
  background-color: #0016b3;
  color: white;
}
</style>
