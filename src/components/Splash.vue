<template>
    <section id="splash">
    <img src="../assets/img/Hero.jpg" id="hero" />
    <img id="logo" src="../assets/icons/logo.svg" />
    <div class="socials">
      <img src="../assets/icons/spotify.svg"/>
      <img src="../assets/icons/instagram.svg"/>
    </div>
  </section>
</template>

<style scoped>
.socials {
  z-index: 2;
  position: absolute;
  bottom: 10px;
  /* right: 0px; */
  margin: auto;
}
.socials img {
  width: 70px;
  margin: 5px;
  transition: opacity 0.3s;
}

.socials img:hover {
  opacity: 0.6;
}

#splash {
    height: 100svh;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: black;
  }

  #splash #hero {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    opacity: 0.7;
    z-index: 1;
    object-fit: cover;
  }
  #splash #logo {
    z-index: 2;
    width: 80%;
    max-width: 500px;
  }
</style>