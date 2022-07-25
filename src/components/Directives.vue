<template>
      <div class="container">
         <h1>Directives</h1>
         <ul>
            <!-- Directive v-for -->
            <button v-on:click="dummyDatas.show =!dummyDatas.show" class="form-control btn btn-secondary">Click to Know</button>
            <li v-for="dummy in dummyDatas" v-bind:key="dummy" v-show="dummy.show">
                <p v-if="dummy.show">Hi this {{dummy.name}} and Iam specialised in {{dummy.specialized}},my current designation is {{dummy.Designation}}</p>
            </li>           
         </ul>
<hr>
         <!-- Directives v-if , v-else -->
         <button @click="interesting = !interesting" class="form-control btn btn-info">Toggle</button>
         <h2 v-if="interesting">Vue is Interesting....!</h2>
         <h2 v-else>Vue is not good.</h2>
<hr>
         <!--V-for with click event using $emit event-->
         <!-- Reference:- https://www.youtube.com/results?search_query=data+communication+in+vue -->
         <div>
            <h2>V-for with click event using $emit event</h2>
              <ul>
               <li v-for="(value,index) in dummyDatas" v-bind:key="index" @click="$emit('clickedData',value)" > {{value.name}} </li>
              </ul>
         </div>
         
      </div>
</template>

<script>
export default {
    name:'Directives',
    props:['dummyDatas'],
    data(){
      return{
         interesting:''
      }
    }

}
</script>

<style scoped>
     .container{
        background-color: brown;
     }
     ul{
        list-style-type: none;
     }
</style>