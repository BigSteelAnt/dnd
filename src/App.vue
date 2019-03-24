<template>
  <div id="app">
    <transition name="slideDown">
<md-card v-if="show" style="animation-duration: 3s" id="title" class="md-elevation-24">
  <md-card-header >
    <div class="md-title">
      Design and Develop1
    </div>
    <div class="md-subhead">
      by Anthony
    </div>
  </md-card-header>
</md-card>
</transition>
<transition name="slideLeft">
<md-card v-if="show" style="animation-duration: 3s" id="card1" class="md-elevation-24">
  <md-card-header>
    <div class="md-title">
      About
    </div>
  </md-card-header>
</md-card>
</transition>
<transition name="slideRight">
<md-card v-if="show" style="animation-duration: 3s" id="card2" class="md-elevation-24">
  <md-card-header>
    <div class="md-title">
      Services
    </div>
  </md-card-header>
</md-card>
</transition>
<transition name="slideUp">
<md-card v-if="show" style="animation-duration: 3s" id="card3" class="md-elevation-24">
  <md-card-header>
    <div class="md-title">
      Technology
    </div>
  </md-card-header>
</md-card>
</transition>
  <transition name="slideUp">
<md-card v-if="show" style="animation-duration: 3s" id="card4" class="md-elevation-24">
  <md-card-header>
    <div class="md-title">
      Contact
    </div>
  </md-card-header>
</md-card>
  </transition>
  </div>
</template>

<script>
export default {
  data () {
    return {
      show: false
    }
  },
  mounted () {
    this.onload()
  },
  methods: {
    onload: function () {
      this.show = true
    }
  },
  name: 'App'
}
</script>

<style>
#app {
  margin-top: 60px;
  margin-left: 30px;
  margin-right: 30px;
}
#card1, #card3 {
    width: 35%;
    padding-bottom: 15%;
    margin: 4px;
    margin-left: 15%;
    display: inline-block;
    vertical-align: top;
}
#card2, #card4 {
    width: 35%;
    padding-bottom: 15%;
    margin: 4px;
    display: inline-block;
    vertical-align: top;
}
#title {
  text-align: center;
}
</style>
