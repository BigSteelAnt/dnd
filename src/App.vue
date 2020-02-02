<template>
  <div id="app">
    <div align="right">
      <label for="locale">Language</label>
      <select v-model="locale">
        <option>en</option>
        <option>ch</option>
      </select>
    </div>
    <transition name="slideDown">
      <md-card v-if="show" style="animation-duration: 3s" id="title" class="md-elevation-24">
        <md-card-header >
        <div class="md-title">
          <p class="line-1 anim-typewriter">Design and Develop</p>
        </div>
        <div class="md-subhead">
          by Anthony
        </div>
        </md-card-header>
      </md-card>
    </transition>
    <transition name="bounce" enter-active-class="bounceInLeft" leave-active-class="bounceOutRight">
      <div v-if="show" style="animation-duration: 3s" class="md-layout md-gutter">
        <md-button class="md-raised md-layout-item" id="buttonYellow" v-on:click="about"><b><h1>{{ $t('about') }}</h1></b></md-button>
        <md-button class="md-raised md-layout-item" id="buttonRed" v-on:click="service"><b><h1>{{ $t('service') }}</h1></b></md-button>
        <md-button class="md-raised md-layout-item" id="buttonBlue" v-on:click="technology"><b><h1>{{ $t('technology') }}</h1></b></md-button>
        <md-button class="md-raised md-layout-item" id="buttonWhite" v-on:click="contact"><b><h1>{{ $t('contact') }}</h1></b></md-button>
      </div>
    </transition>
    <transition name="bounce" enter-active-class="bounceInLeft" leave-active-class="bounceOutRight">
      <div v-if="aboutPage">
        <md-content id="aboutContentBox">{{ $t('aboutContent') }}</md-content>
      </div>
    </transition>
        <transition name="bounce" enter-active-class="bounceInLeft" leave-active-class="bounceOutRight">
      <div v-if="servicePage">
        <md-content id="serviceContentBox">{{ $t('serviceContent') }}</md-content>
      </div>
    </transition>
        <transition name="bounce" enter-active-class="bounceInLeft" leave-active-class="bounceOutRight">
      <div v-if="technologyPage">
        <md-content id="technologyContentBox">{{ $t('technologyContent') }}</md-content>
      </div>
    </transition>
        <transition name="bounce" enter-active-class="bounceInLeft" leave-active-class="bounceOutRight">
      <div v-if="contactPage">
        <md-content id="contactContentBox">{{ $t('contactContent') }}</md-content>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data () {
    this.$i18n.locale = 'en'
    return {
      locale: 'en',
      show: false,
      aboutPage: false,
      servicePage: false,
      technologyPage: false,
      contactPage: false
    }
  },
  watch: {
    locale (val) {
      this.$i18n.locale = val
    }
  },
  mounted () {
    this.onload()
  },
  methods: {
    onload: function () {
      this.show = true
    },
    about: function () {
      this.aboutPage = true
      this.servicePage = false
      this.technologyPage = false
      this.contactPage = false
    },
    service: function () {
      this.aboutPage = false
      this.servicePage = true
      this.technologyPage = false
      this.contactPage = false
    },
    technology: function () {
      this.aboutPage = false
      this.servicePage = false
      this.technologyPage = true
      this.contactPage = false
    },
    contact: function () {
      this.aboutPage = false
      this.servicePage = false
      this.technologyPage = false
      this.contactPage = true
    }
  },
  name: 'App'
}
</script>

<style lang="scss">
@import "~vue-material/dist/theme/engine";
@include md-register-theme("default-dark", (
  primary: md-get-palette-color(blue, A200), // The primary color of your application
  accent: md-get-palette-color(yellow, A200), // The accent or secondary color
  theme: dark
));
@import "~vue-material/dist/theme/all";
.md-content {
    width: 100%;
    height: 70vh;
    display: inline-flex
}
#aboutContentBox {
  background: orange;
  color:black;
}
#serviceContentBox {
  background: #ffccff;
  color:black;
}
#technologyContentBox {
  background: #ccff99;
  color:black;
}
#contactContentBox {
  background: White;
  color:black;
}
#buttonYellow {
  background: yellow;
  color:black;
}
#buttonRed {
  background: red;
  color:white;
}
#buttonBlue {
  background: blue;
  color:white;
}
#buttonWhite {
  background: white;
  color:black;
}
#app {
  margin-top: 60px;
  margin-left: 30px;
  margin-right: 30px;
}
#title {
  text-align: center;
}
.line-1{
    position: relative;
    top: 50%;
    width: 24em;
    margin: 0 auto;
    border-right: 2px solid rgba(255,255,255,.75);
    font-size: 100%;
    text-align: center;
    white-space: nowrap;
    overflow: hidden;
    transform: translateY(-50%);
}
/* Animation */
.anim-typewriter{
  animation: typewriter 4s steps(44) 1s 1 normal both, blinkTextCursor 500ms steps(44) infinite normal;
}
@keyframes typewriter{
  from{width: 0;}
  to{width: 10em;}
}
@keyframes blinkTextCursor{
  from{border-right-color: rgba(255,255,255,.75);}
  to{border-right-color: transparent;}
}
</style>
