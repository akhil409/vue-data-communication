<template>
       <div class="container">
            <h1>Events in Vue</h1>
            <p>My age is {{age}}</p>
            <button v-on:click="add(1)">Add Year</button>
            <button v-on:click="sub(1)">Subtract Year</button>
            <button v-on:dblclick="add(10)">Add 10 years</button>
            <button v-on:dblclick="sub(10)">Subtract 10 years</button>
            <div id="coordinates" v-on:mousemove="updateOffSet">Coordinates are ({{x}},{{y}})</div>
       </div>
</template>

<script>
export default {
        name:'Events',
        data(){
            return{
                age:10,
                x:0,
                y:0,
            }
        },
        methods:{
           add(inc){
               this.age+=inc
           },
           sub(dec){
              this.age-=dec
           },
           updateOffSet(event){
              this.x = event.offsetX;
              this.y = event.offsetY; 
           }
        }
}
</script>

<style scoped>
   .container{
    background-color: chartreuse;
   }
   #coordinates{
     display: flex;
     justify-content: center;
     align-items: center;
     font-weight: bold;
   }
</style>