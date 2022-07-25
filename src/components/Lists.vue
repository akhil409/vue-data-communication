<template>
      <div class="container">
             <h1>List & Keys Rendering in Vue.js</h1>
             <ul>
                <li v-for="(name, index) in names" v-bind:key="index">{{name}}</li>
             </ul>
             <hr>
             <!--  -->
             <ul>
                <li v-for="(name,index) in fullNames" v-bind:key="index">{{name.firstName}} {{name.lastName}}</li>
             </ul>
             <hr>
             <!--  -->
             <div v-for="(actor,index) in actors" v-bind:key="index">
                <h2>{{actor.name}}</h2>
                <p v-for="(movie,index) in actor.movies" v-bind:key="index">{{movie}}</p>
             </div>

             <!--  -->
             <ul>
                <li v-for="(value,key,index) in myInfo" v-bind:key="index">
                    {{index}} {{key}}  {{value}}
                </li>
             </ul>
            <!--  -->
             <template v-for="star in stars" >
                         {{star}}
             </template>
             
      </div>
</template>

<script>
export default {
       name:'Lists',
       data(){
          return{
              names:['Johnny','Chris','Leonardo'],
              stars:['Robert Downey Jr.','Brad Pitt','Sylvester Stallone'],
              fullNames:[{firstName:'Tom',lastName:'Cruise'},
                         {firstName:'Arnold',lastName:'Schwarzenegger'},
                         {firstName:'Will',lastName:'Smith'}],
              actors:[{name:'Tom Cruise',movies:['Knight and Day','Vanilla Sky','Mission: Impossible']},
                       {name:'Arnold Schwarzenegger ',movies:['The Terminator','True Lies','Predator']},
                       {name:'Will Smith',movies:['Aladdin','Suicide Squad','I Am Legend']}],
              myInfo:{
                     Name:'Cameroon Diaz',
                     Designation:'Actress',
                     Age:49,
                     Height:1.74,
              }
          }
       }

}
</script>

<style scoped>
    ul{
        list-style-type: none;
    }
</style>