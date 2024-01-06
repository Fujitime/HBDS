<template>
  <div ref="app">
    <canvas class="confetti" id="canvas"></canvas>
    <Balon />
    <BirthdayCard /> 
  </div>
</template>

<script>
import Balon from './components/Ballon.vue';
import BirthdayCard from './components/BirthdayCard.vue'; 
import music from './assets/music.mp3';

export default {
  components: {
    Balon,
    BirthdayCard,
  },
  mounted() {
    const playMusicOnce = () => {
      const audio = new Audio(music);
      audio.play();
      document.removeEventListener('click', playMusicOnce);
    };
    document.addEventListener('click', playMusicOnce);
  },
};
</script>
