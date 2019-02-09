<template>
  <div>
    <h2>Mission Statement</h2>
    <p>{{ mission }} </p>
  </div>
</template>

<script>
export default {
  name: 'Statement',
  data: function(){
    return {
      'mission': 'RA develops technology to empower participants of the civil society. For a properly functioning democracy it is essential to have a functioning third space. Yet the recent data revolution have caused an inequality between those who have access and those who have not.'
    }
  }
}
</script>

<style scoped>
h2 {
  font-family: "Fedra Mono Medium";
  font-size: .9rem;
  font-weight: 100;
  text-transform: uppercase;
}

p {
  font-family: 'Feijoa-Medium';
  font-weight: 300;
  font-size: 1.3rem;
  line-height: 1.8rem;
}

div {
  margin-left: 33.33%;
  width: 33.33%;
  text-align: center;
  margin-bottom: 3rem;
  z-index: 10;
  position: absolute;
}
</style>