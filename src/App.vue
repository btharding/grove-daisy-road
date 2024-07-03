<script setup>
import Release from './components/Release.vue'
import Event from './components/Event.vue'
import Splash from './components/Splash.vue'
</script>

<script>
  export default {
    name: 'App',
    components: {
      Event,
      Splash,
      Release,
    },
    data: function () {
      return {
        releases: [
          {
            releaseName: "Right Hand Man",
            releaseLinks: [
              {
                title: "Spotify",
              },
              {
                title: "Youtube"
              },
              {
                title: "SoundCloud"
              }
            ],
            trackList: [
              {
                no: 1,
                name: "Right hand man",
                length: "4:25"
              },
              {
                no: 2,
                name: "Lorem Ipsum",
                length: "45:16"
              }
            ],
            trackImgFilename: "album.jpg"
          }
        ],
        events: [
          {
            date: "01/02/2023",
            city: "Birmingham",
            venue: "Sunflower Lounge"
          }
        ],
        gallery: [
          './assets/img/Hero.jpg'
        ]
      }
    },
    methods: {
      formatImgUrl: function (filename) {
        return new URL(`${filename}`, import.meta.url).href;
      }
    }
  }
</script>

<template>
  <Splash />
  <section id="watch">
    <h1>WATCH</h1>
    <Event v-for="event in events" v-bind="event"/>
    </section>
  <section id="listen">
    <h1>LISTEN</h1>
    <Release v-for="release in releases" v-bind="release"/>
  </section>
  <section id="gallery">
    <h1>GALLERY</h1>
    <div class="gallery-container">
    <img v-for="image in gallery" :src="formatImgUrl(image)" />
    </div>
  </section>
</template>

<style scoped>

.gallery-container {
  width: 90%;
  max-width: 1000px;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
  gap: 15px;
  margin: auto;
}

.gallery-container img {
  width: 100%;
  object-fit: cover;
}


section {
  text-align: center;
  padding-top: 10px;
}


  section#listen {
  }
</style>
