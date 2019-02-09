<template>
  <div id="app">
    <Header />
    <!-- <div id="container"></div> -->
    <Statement />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Statement from './components/Statement.vue';

import * as Three from 'three';
var OrbitControls = require('three-orbit-controls')(Three)


export default {
  name: 'app',
  data() {
    return {
      camera: null,
      scene: null,
      renderer: null,
      mesh: null
    }
  },
  components: {
    'Header': Header,
    'Statement': Statement
  },
  methods: {
    init: function() {
      let container = document.getElementById('container');

      this.camera = new Three.PerspectiveCamera(70, container.clientWidth/container.clientHeight, 1, 1000);
      this.camera.position.z = 1;

      this.scene = new Three.Scene();

      this.scene.background = new Three.Color( 0x7876BC );

      var grid = new Three.GridHelper(10, 10, 100, 64, 0x0000ff, 0x808080);
      // grid.position.y = 150;
			// grid.position.x = 150;
      this.scene.add(grid);

      let geometry = new Three.BoxGeometry(0.2, 0.2, 0.2);
      let material = new Three.MeshNormalMaterial();

      this.mesh = new Three.Mesh(geometry, material);
      this.scene.add(this.mesh);

      this.controls = new OrbitControls(this.camera)



      this.renderer = new Three.WebGLRenderer({antialias: true});
      this.renderer.setSize(container.clientWidth, container.clientHeight);
      container.appendChild(this.renderer.domElement);


    },
    animate: function() {
      requestAnimationFrame(this.animate);
      this.mesh.rotation.x += 0.01;
      this.mesh.rotation.y += 0.02;
      this.renderer.render(this.scene, this.camera);
    }
  },
  mounted() {
    this.init();
    this.animate();
  }
}
</script>

<style>
@font-face {
  font-family: 'Feijoa-Medium';
  src: url('./assets/fonts/FeijoaWeb-Medium.woff') format('woff'); /* Pretty Modern Browsers */
}

@font-face {
  font-family: "Fedra Mono Medium";
  src: url("https://s3-eu-west-1.amazonaws.com/fonts-ireland.typotheque.com/WF-031221-010286-000064-be8bfee213f84bde3a73ed8266427105.eot");
  src: url("https://s3-eu-west-1.amazonaws.com/fonts-ireland.typotheque.com/WF-031221-010286-000064-be8bfee213f84bde3a73ed8266427105.eot?#iefix") format("embedded-opentype"), url("https://s3-eu-west-1.amazonaws.com/fonts-ireland.typotheque.com/WF-031221-010286-000064-be8bfee213f84bde3a73ed8266427105.woff2") format("woff2"), url("https://s3-eu-west-1.amazonaws.com/fonts-ireland.typotheque.com/WF-031221-010286-000064-be8bfee213f84bde3a73ed8266427105.woff") format("woff"), url("https://s3-eu-west-1.amazonaws.com/fonts-ireland.typotheque.com/WF-031221-010286-000064-be8bfee213f84bde3a73ed8266427105.svg#typotheque_webfonts_service") format("svg");
}

body {
  margin: 0 !important;
  font-size: 22px;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: -20px;
}

#container {
  width: 100%;
  height: 100vh;
}
</style>
