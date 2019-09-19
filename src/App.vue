<template>
  <div id="app">


     Parent: <input type="text" v-model="goodValue">{{goodValue}}
    <hr />
    <img alt="Vue logo" src="./assets/logo.png">
    <Header @transfer="getValue" :propValue="goodValue"/>
    <Contacts :propValue="goodValue"/>
    <Messages msg="Welcome to Your Messages.js App"/>
    <Footer msg="Welcome to Your Footer.js App"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Contacts from './components/Contacts.vue'
import Messages from './components/Messages.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'app',
   data(){
     return {
       goodValue: ''
     }
   },
  methods: {
    getValue(value) {
      console.log('Working ..getValue', value)
      this.goodValue = value;
    }
  },
  components: {
    Header: Header,
    Contacts: Contacts,
    Messages: Messages,
    Footer: Footer,
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
