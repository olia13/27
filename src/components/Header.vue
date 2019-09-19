<template>
  <div class="head">
    
    Search: <input type="text" v-bind:value="propValue" @input="onInput">
    <div></div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props:['propValue'],
  methods: {
    onInput(event) {
        console.log(event.target.value, 'value in child')
        this.$emit('transfer', event.target.value);
      }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.head {
  height:200px;
  border: 1px solid blue;
  
}

</style>
