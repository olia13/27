<template>
  <div class="mas">
    <h1>{{ msg }}</h1>
    
  </div>
</template>

<script>
export default {
  name: 'Messages',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.mas {
  border: 1px solid red;
  width: 50%;
  height: 800px;
  
}

</style>
