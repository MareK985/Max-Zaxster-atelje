<template>
  <div class="hero">
    <div class="outremer">
      {{ $t('outremerTitle') }}
    </div>
    <input id="check" class="check" type="checkbox">
    <header :class="{scrolling: scrollPosition > 500}">
      <NuxtLink to="/MaxZaxster">
        <font-awesome-icon class="back-btn" :icon="['fas', 'chevron-left']" />
      </NuxtLink>
      <div class="navigation">
        <a href="#footer">{{ $t('contact') }}</a>
        <!-- <router-link class="login-btn" :to="{}">Login</router-link> -->
      </div>
      <label for="check">
        <font-awesome-icon id="menu-btn" :icon="['fas', 'bars']" />
        <font-awesome-icon id="close-btn" :icon="['fas', 'times']" />
      </label>
      <nuxt-link
        v-for="locale in availableLocales"
        :key="locale.code"
        class="languageToggle"
        :to="switchLocalePath(locale.code)"
      >
        {{ locale.name }}
      </nuxt-link>
    </header>
    <!-- <div class="svg-animation">
        <img src="../assets/static/images/undraw_shopping_app_flsj.svg">
       </div> -->
    <!-- <div class="content">
        <div class="info">
          <h2>Experience shopping <br><span>in your unit</span></h2>
            <p>Platform designed as a multi-unit on-demand m-commerce web application. </p>
          </div>
        </div> -->
  </div>
</template>

<script>
export default {
	data () {
		return {
			scrollPosition: 0
		}
	},
	computed: {
		availableLocales () {
			return this.$i18n.locales.filter(i => i.code !== this.$i18n.locale)
		}
	},
	mounted () {
		window.addEventListener('scroll', this.handleTopBar)
	},
	methods: {
		handleTopBar () {
			this.scrollPosition = window.scrollY
		}
	}
}
</script>

<style lang="scss" scoped>

@import "./../static/fonts/stylesheet.css";

:root {
  --bg: rgb(44, 62, 80);
  --bg-light: rgb(56, 80, 104);
  --primary: #b97b42;
  --bright: #ffffff;
  --gray: #1b1e25;
}

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: sans-serif;
}

.pricing-header h3 {
  font-size: 4em;
  margin-bottom: 0.5em;
}

.back-btn {
  color: white;
  font-size: 40px;
}

.back-btn:hover {
  color: rgba(0, 0, 0, 0.7);
}

.outremer {
  font-family: "HennyPennyRegular";
  font-size: 7vh;
  font-weight: bold;
  text-align: center;
  color: white;
  padding-top: 40%;
}

// .gold {
//     background: url("../assets/bg/gold_bg.jpg");
//     background-size: cover;
//     color: #fff;
//     -webkit-text-fill-color: transparent;
//     -webkit-background-clip: text;
// }

section{
  position: relative;
  width: 100%;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}
.hero {
  height: 100vh;
  background: url("../assets/img/outremer/outremer_hero.jpg")no-repeat;
  background-size: cover;
  background-position: center;

}

header {
  top: 0;
  width: 100%;
  padding: 30px 100px;
  display: flex;
  position: fixed;
  justify-content: space-between;
  align-items: center;
  z-index: 100;
}

.scrolling {
  background: url("../assets/img/bg/stickyHeaderBg-blue.jpg")no-repeat;
	background-size: cover;
  opacity: 1;
	animation-name: fadeInOpacity;
	animation-iteration-count: 1;
	animation-timing-function: ease-in;
	animation-duration: 1s;
  z-index: 10;
}

@keyframes fadeInOpacity {
	0% {
		opacity: 0;
	}
	100% {
		opacity: 1;
	}
}

header .logo{
  position: relative;
  /* color: var(--bright); */
  color: #fff;
  font-size: 30px;
  text-decoration: none;
  text-transform: uppercase;
  font-weight: 800;
  letter-spacing: 1px;
}

header .navigation a{
    color: #fff;
    text-decoration: none;
    font-weight: 500;
    letter-spacing: 3px;
    margin-left: 10px;
    padding: 10px 10px;
    border-radius: 1px;
    transition: 0.3s;
    transition-property: background;
}

header .navigation a:not(:last-child){
  margin-right: 30px;
}

header .navigation a:hover{
  background: rgba(255, 255, 255, 0.2);
}

.languageToggle {
    color: white;
    text-decoration: none;
    right: 40px;
    padding: 0;
    position: absolute;
}

// .content .info{
// background-color: var(--bg-light) !important;
// padding: 20px;
// }

.content .info h2{
  text-align: left;
  color: var(--primary);
  font-size: 55px;
  text-transform: uppercase;
  font-weight: 400;
  letter-spacing: 2px;
  line-height: 60px;
  margin-bottom: 30px;
}

.content .info h2 span{
  color: #fff;
  font-size: 50px;
  font-weight: 600;
}

.content .info p{
  color: #fff;
  font-size: 30px;
  text-align: justify;
  font-weight: 500;
  margin-bottom: 40px;
}
.navigation .login-btn
{
  color: #fff;
  background: var(--primary);
  text-decoration: none;
  text-transform: uppercase;
  font-weight: 500;
  letter-spacing: 2px;
  padding: 10px 20px;
  border-radius: 5px;
  transition: 0.3s;
  transition-property: background;
}

.navigation .login-btn:hover{
  background: #0C4F60;
}

.content .info-btn
{
  color: #fff;
  background: #0C4F60;
  text-decoration: none;
  text-transform: uppercase;
  font-weight: 500;
  letter-spacing: 2px;
  padding: 10px 20px;
  border-radius: 5px;
  transition: 0.3s;
  transition-property: background;
}

.content .info-btn:hover{
  background: #0C4F60;
}

.media-icons{
  position: absolute;
  bottom: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
  margin-bottom: 20px;
   left: 50%;
  transform: translateX(-50%);
}

.media-icons a{
  position: relative;
  color: #fff;

  font-size: 25px;
  transition: 0.3s;
  transition-property: transform;
}

.media-icons a:not(:last-child){
  margin-right: 60px;
  color: #fff;

}

.media-icons a:hover{
  transform: scale(1.5);
  color: rgba(0, 0, 0, 0.7);
}

label{
  display: none;
}

.check {
color: white;
}

#check{
  z-index: 3;
  display: none;

}

  .footerColumn {
    text-align: left;
  }
  footer h5 {
    padding-left: 24px;
  }
/* Responsive styles */

@media (max-width: 960px){
  .languageToggle {
    right: 80px;
    padding: 0;
    position: absolute;
}
  header {
        padding: 30px 30px;
  }
  header .navigation{
    display: none;
  }

  label{
    display: block;
    font-size: 25px;
    cursor: pointer;
    transition: 0.05s;
    transition-property: color;
    color: white;
  }

  // label:hover{
  // color: rgba(0, 0, 0, 0.7);
  // }

  label #close-btn{
    display: none;
  }

  label #close-btn #menu_btn{
  }

  #check:checked ~ header .navigation{
    z-index: 2;
    position: fixed;
    background: rgba(27, 30, 37, 0.8);
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  #check:checked ~ header .navigation a{
    font-weight: 700;
    margin-right: 0;
    margin-bottom: 50px;
    letter-spacing: 2px;
  }
  #check:checked ~ header label #menu-btn{
    display: none;
  }
  #check:checked ~ header label #close-btn{
    z-index: 2;
    display: block;
    position: fixed;
  }
  label .menu-btn{
    position: absolute;
  }
  header .logo{
    position: absolute;
    font-size: 20px;
    top: 35px;
  }
  .content .info h2{
    font-size: 45px;
    line-height: 50px;
  }
  .content .info h2 span{
    font-size: 40px;
    font-weight: 600;
  }
  .content .info p{
    font-size: 18px;
  }
}

@media (max-width: 560px){
    header {
    padding: 10px !important;
  }
  .hero {
  background: url("../assets/img/outremer/outremer_hero_mobile.jpg")no-repeat;
  background-size: cover;
  background-position: center;
}
  .content {
      margin: 70px 30px;
  }
  .content .info h2{
    font-size: 35px;
    line-height: 40px;
  }
  .content .info h2 span{
    font-size: 30px;
    font-weight: 600;
  }
  .content .info p{
    font-size: 14px;
  }
.card-deck .card {
  min-width: 220px;
  padding: 10px;
}

.back-btn {
  font-size: 20px;
}
.outremer {
  padding-top: 100%;
}
}

/* END OF HEADER / HERO syles */

/* OUR SERVICE syles */

@media (min-width: 768px) {
  html {
    font-size: 16px;
  }
}

.container {
  max-width: 1300px;
}

.pricing-header {
  max-width: 700px;
}

.card-deck .card {
  min-width: 220px;
}

.border-top { border-top: 1px solid #e5e5e5; }
.border-bottom { border-bottom: 1px solid #e5e5e5; }

.box-shadow { box-shadow: 0 .25rem .75rem rgba(0, 0, 0, .05); }

</style>
