<template>
  <div class="head">
  <h1>{{msg}}</h1>
    Search: <input type="text" @input="onInput">

    <ul class="ex">
      <li 
        v-for="item in this.propValueBack"
        :key="item.id">
        {{ item.name }}
          <ul class="ex">
            <li 
              v-for="item in item.messages"
              :key="item.id">
                {{ item }}...
                         
            </li>
          </ul>
      </li>
    </ul>


    
  </div>
</template>

<script>
export default {
  name: 'Header',
  props:{
    ['propValueBack']: Array,
    msg: String,
  },
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
.ex {
  list-style-type: none;
  
}
.ex li {
  float: left;
}

.head {
  height:200px;
  border: 1px solid blue;
  
}



</style>
