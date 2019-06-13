<template>
  <div id="app">
    <div id="nav">
     
    </div>
    <router-view/>
    
     <table>
       <tr>
         <td>id</td>
         <td>IMEI</td>
         <td>device</td>
         <td>message</td>
         <td>tel</td>
       </tr>
       <tr v-for='index in syk'>
          <td> {{index.id}}</td>
       <td>{{index.IMEI}}</td>
       <td> {{index.tel}}</td>
          <td> {{index.message}}</td>
    <td> {{index.tel}}</td>
      
       </tr>
     </table>
     <button @click="mu">55</button>
     

    
  </div>
</template>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
table{
    table-layout:fixed;
    empty-cells:show; 
    border-collapse: collapse;
    margin:0 auto;
    border: 2px solid black
}
td{
  border: 1px solid black;
    height:20px;
}
</style>
<script>
export default {

  name: "app",
  
  

  data(){
    return{
      syk:''
    }
  },


// created(){
//       this.axios.get('http://localhost:60020/all').then((response)=>{
//         console.log(response.data.data[1]);
//         this.syk=response.data.data;

//         console.log(this.syk);
//       }).catch((error)=>{
//           console.log(error)
//       })
//     },
    methods:{

      mu(){
      this.axios.get('http://localhost:60020/all').then((response)=>{
        console.log(response.data.data[1]);
        this.syk=response.data.data;

        console.log(this.syk);
      }).catch((error)=>{
          console.log(error)
      })
    }
    }
  
};
</script>
