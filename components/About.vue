<template>
  <div>
    <div class="about-container">
      <div class="about-img">
        <img class="responsive" src="~assets/img/about_slika.jpg">
      </div>
      <div class="about-text" data-aos="fade-left" data-aos-duration="1500">
        <p style="font-style: italic" class="predgovor">
          {{ $t('predgovor1') }}
        </p><br>
        <p class="predgovor">
          {{ $t('predgovor2') }}
        </p>
        <p class="read-more">
          <a @click="$refs.about.open()">{{ $t('readMore') }}</a>
        </p>
      </div>
      <sweet-modal ref="about" modal-theme="dark" overlay-theme="dark">
        <p class="predgovorModal">
          {{ $t('predgovor1') }}
          {{ $t('predgovor2') }}
        </p>
      </sweet-modal>
    </div>
  </div>
</template>

<script>

</script>

<style lang="css" scoped>

.about-container {
  padding: 15px;
}
.responsive {
  width: 100%;
  height: auto;
}
.about-img {
  display: inline-block;
  max-width: 50%;
  text-align: left;
  padding: 2em;
  margin: 5px;
  vertical-align: top;
}
.about-text {
  position: relative;
  overflow: hidden;
  max-height: 400px;
  z-index: 100;
  display: inline-block;
  color: rgba(255,255,255, 0.77);
  background: rgb(80, 79, 79) !important;
  max-width: 50%;
  text-align: left;
  padding: 20px;
  margin: 80px 0px 0px -100px;
}
.predgovor {
  font-size: 1.2rem;
  padding: 10px;
  text-align: justify;
  letter-spacing: 2px;
  line-height: 1.8em;
}
.about-text .read-more {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  text-align: center;
  margin: 0;
  padding: 30px 0;
  cursor: pointer;
  /* "transparent" only works here because == rgba(0,0,0,0) */
  background-image: linear-gradient(to bottom, transparent,  rgb(29, 28, 28));
}

@media only screen and (max-width: 1500px) {
    .about-text {
        max-width: 50%;
        margin: 20px 0px 0px -100px !important;
    }
    .predgovor {
  font-size: 1.0rem;
  letter-spacing: 1px;
  line-height: 1.4em;
}
}
@media only screen and (max-width: 980px) {
    .about-img {
        max-width: 100%;
    }
    .about-text {
    margin: 0px 0px 0px 40px !important;
    max-width: 100%;

    }
  .predgovor {
    font-size: 1.9vh;
    text-align: justify;
    padding: 10px 20px;
    line-height: 1.3em;
  }
}
@media only screen and (max-width: 749px) {
  .about-img {
    max-width: 100%;
    padding: 0em;
    margin: 5px;
    vertical-align: top;
  }
  .about-text {
    margin: 0px !important;
    max-width: 100%;
  }

  .predgovor {
    font-size: 1.8vh;
    text-align: justify;
    padding: 10px 20px;
    line-height: 1.3em;
  }
}

@media only screen and (max-width: 500px) {
  .about-text {
    margin: -20px 0px 0px 0px !important;
    max-width: 100%;
    padding: 5px;
  }
  .about-img {
    max-width: 100%;
  }
  .predgovor {
    font-size: 1.6vh;
    text-align: justify;
    line-height: 1.5em;
  }
}

</style>
