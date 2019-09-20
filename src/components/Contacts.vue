<template>
  <div class="cont">
  <h1>{{msg}}</h1>  
   
    
    <div>{{getFullName}}</div> 
    
   
  </div>
</template>

<script>
export default {
  name: 'Contacts',
  props:{
    ['propValue']: Array,
    msg: String,
  },


  
  data() {
    return {
      newArray:'',
      array: [{name:'Ann', messages:['hello', 'Goodbay']}, 
              {name:'Bob', messages:['hello', 'Goodbay']}, 
              {name:'Cat', messages:['hello', 'Goodbay']},]
    }
  },
  computed: {
    getFullName() {
     
      var value = this.propValue;
     
      this.newArray = this.array.filter(function (item){
        
        return item.name.indexOf(value) >= 0;
      });
      
      this.$emit('transferBack', this.newArray);
       
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.cont {
  border: 1px solid red;
  width: 50%;
  height: 400px;
  float: right;
  box-sizing: border-box;
}
</style>
