<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <br/>
    <span>  {{ message1 }}  </span><br/>
    <span v-text="message2"></span>
    <hr/>
    <span> {{ counter }} </span> <br/>
    <button v-on:click="counter=counter+1" >+</button>
    <button v-on:click="minus" >-</button>
    <hr/>
    <span>  {{ message3 }}  </span><br/>
    <input type="text" v-model="message3"/>
    <select v-model="message3">
      <option value="choice01">Hello 1 </option>
      <option value="choice02">Hello 2 </option>
      <option value="choice03">Hello 3 </option>
    </select><br/><br/>
    <textarea v-model="message3"></textarea>
    <hr/>
    <input v-bind:type="inputtype" />xxx<br/>
    
    <img v-bind:src="require('@/assets/images/'+imagename)">
    <select v-model="imagename">
      <option value="maxresdefault.jpg">Image 1 </option>
      <option value="Untitled-1.jpg">Image 2 </option>
  </select><br/><br/><br/>
  <hr/>

  <h1 v-show="isGreeting"> Hello !!! </h1>
  
  <hr/>
  {{htmlText}}<br/>
  <span v-html="htmlText"></span>
  
  <hr/>
  <div v-bind:key="emp.id" v-for="emp in employees">
    <b>Id</b>: {{emp.id}},<br/>
    <b>Name</b>: {{emp.name}},<br/>
    <b>Salary</b>: {{emp.Salary}},<br/><br/><br/>
    <b>Name</b>:<span v-bind:class="(emp.Salary>90000) ? 'high' : (emp.Salary>=30000) ? 'medium' : 'low' ">{{emp.name}}</span>,<br/> 
    <b>Salary</b>:{{emp.Salary}},
    <span  v-if="emp.Salary>90000">***</span>
    <span  v-else-if="emp.Salary>=30000">**</span>
    <span  v-else>*</span>


    <br/><br/><br/> 


 
 
  </div>
  <hr/>
  <div v-bind:key="std.studentId" v-for="std in students"> 
    <b>studentId :</b> {{std.studentId}},<br/>
    <b>firstame :</b> {{std.firstname}},<br/>
    <b>lastName :</b> {{std.lastName}},<br/>
    <b>score :</b> {{std.score}},<br/><br/><br/>
  </div>




<!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'


export default {
  name: 'App',
  components: {
    //HelloWorld
  },
  data(){
    return {
      message1: "Hello World !!",
      message2: "Hello World Again !!",
      message3: "Type Here!",
      inputtype: "radio",
      imagename:"maxresdefault.jpg",
      htmlText: "<b>HTML TEXT</b>&nbsp:",
      counter: 0,
      isGreeting: true,
      employees:[{"id":1,"name":"John","Salary":30000},{"id":2,"name":"Trump","Salary":10000},{"id":3,"name":"Peter","Salary":99000}],
      students:[{"studentId":624235055,"firstname": "Phongpol","lastName":"Nitiweroj","score":"100"},{"studentId":624235048,"firstname": "Warinthon","lastName":"Kongjan","score":"100"},{"studentId":624235054,"firstname":"Sofwan","lastName":"Jehmusa","score":"100"},{"studentId":624235052,"firstname": "wanasaree","lastName":"sahasantivarakul","score":"100"}]
    }
  },
  methods: {
    minus: function() {
      this.counter=this.counter-2
    }
  }
}
</script>




<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.high{
  color: rgb(41, 6, 167);
}
.medium{
  color: rgb(4, 68, 187);
}
.low{
  color: rgb(9, 152, 247);
}
</style>
