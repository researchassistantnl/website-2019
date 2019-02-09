<template>
  <div class="header">
    <Blinds />
    <img class="logo" src="../assets/logo.svg" />
    <h1>Technology for a<br/>stronger civil society</h1>
  </div>
</template>

<script>
import Blinds from './Blinds.vue';

export default {
  name: 'Header',
  props: {
    msg: String
  },
  components: {
    'Blinds': Blinds
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  width: 100%;
  height: 100vh;
  background-image: url('../assets/ascii-optimized.png');
  background-size: 80%;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

h1 {
  font-family: 'Feijoa-Medium';
  font-weight: 300;
  font-size: 3rem;
  width: 50%;
  line-height: 3.2rem;
  margin-left: 5%;
}

.logo {
  width: 3rem;
  margin-left: 5%;
}
</style>
