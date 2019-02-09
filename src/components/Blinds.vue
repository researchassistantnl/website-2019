<template>
  <div class="blinds">
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>
    <div class="blind">
        <div class="closing-blind"></div>
    </div>				
  </div>
</template>

<script>
/* eslint-disable */
import anime from 'animejs';

export default {
  name: 'Blinds',
  props: {
    msg: String
  },
  mounted() {
		window.setTimeout(this.blinds, 3000)
	},
	methods: {
		blinds() {

			anime({
				targets: '.closing-blind',
				width: '100%',
				height: '100vh',
				duration: 200,
				delay: anime.stagger(100),
				easing: 'easeInOutExpo'
			});
		}
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.blinds {
    width: 100%;
    height: 100vh;
    position: fixed;
    z-index: 5;
}

.blind {
    width: 5%;
    float: left;
}

.closing-blind {
    width: 0;
    /* height: 100vh; */
    background: white;
}
</style>
