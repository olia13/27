<template>
  <div class="cont">
    <!-- Search: <textarea type="text" v-bind:value="propValue"> </textarea>   -->
   
    <!-- <button @click="getFullName">jjj</button> -->
    <div>{{getFullName}}</div>
    
   
  </div>
</template>

<script>
export default {
  name: 'Contacts',
  props:['propValue'],
  data() {
    return {
      newArray:'',
      array: [{name:'Ann', messages:['hello', 'Goodbay']}, {name:'Bob', messages:['hello', 'Goodbay']}, {name:'Cat', messages:['hello', 'Goodbay']},]
    }
  },
  computed: {
    getFullName() {
     
     //var matches_array = str.match(regexp);

     var value = this.propValue;
     
      this.newArray = this.array.filter(function (item){
            console.log(item.name);
            return item.name.indexOf(value) >= 0;
        });
      
      return this.newArray
       
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.cont {
  border: 1px solid red;
  width: 50%;
  height: 800px;
  float: right;
}
</style>
