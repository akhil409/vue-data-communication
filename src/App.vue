<!--Props data passsing from Parent to Child--> 
<template>
      <div class="container">
            <div class="propsPC">
<!-- Dynamic Data Passing from Parent to Child -->
             <app-data v-bind:dummyDatas="dummyDatas"></app-data>
<!-- Static Data Passing-->             
             <button @click="title='Avengers End Game'" class="form-control btn btn-primary">Click</button>
             {{title}}
<hr>
<!-- Static Data Passing from Parent to Child -->
             <app-data v-bind:actressName="actressName" v-bind:actorName="actorName" v-bind:film="film"></app-data>

         </div>
<hr> 
            <div class="eventCP">
<!-- Passing Data from Child to Parent using Props -->
             <h1>Passing Data from Child to Parent using Props</h1>
             <PropsChildToParent v-on:changeData="updateChild($event)"/> <br>
             <p>{{parentData}}</p>
             </div>
<hr>
            <div class="eventBus">
<!-- Using Event Bus (Communication between any two components) -->
             <h1>Event Bus - Communication between any two components</h1>
             <EventBus1 />
             <EventBus2 />
             </div>
<hr>
            <div class="provideInject">
<!-- Provide/Inject (Parent to child communication) -->
              <ProvideInject />
            </div>
<hr>
            <div class="refParentChild">            
<!--Using this.$refs (Parent to Child Communication)-->
              <RefParentChild ref="child"/>
              <button v-on:click="refData=!refData">Click</button>
              {{ refData }}
            </div>
<hr>
            <div class="events">
<!-- Events in Vue.js  -->
               <Events />
            </div>
<hr>
            <div class="directives">
<!-- Vue Directives -->
               <Directives v-bind:dummyDatas="dummyDatas" @clickedData="getClickData"/>
               <p >Hi this is <span>{{getData.name}}</span> and Iam from specialised in <span>{{getData.specialized}}</span>  and my current designation is <span>{{getData.Designation}}</span></p>
            </div>
<hr>
            <div class="conRend">
<!-- Conditional Rendering -->
                <ConditionRendering />
            </div>
<!-- Lists & Keys -->
            <div class="listsKeys">
                <Lists />
            </div>
      </div>
</template>

<script>

import PropsParentToChild from './components/PropsParentToChild.vue';
import PropsChildToParent from './components/PropsChildToParent.vue';
import EventBus1 from './components/Event-Bus1.vue';
import EventBus2 from './components/Event-Bus2.vue';
import ProvideInject from './components/Provide-Inject.vue';
import RefParentChild from './components/RefParentChild.vue';
import Events from './components/Events.vue';
import Directives from './components/Directives.vue';
import ConditionRendering from './components/ConditionRendering.vue';
import Lists from './components/Lists.vue';

export default {
    name:'App',
    components: {
    "app-data": PropsParentToChild,
    PropsChildToParent,
    EventBus1,
    EventBus2,
    ProvideInject,
    RefParentChild,
    Events,
    Directives,
    ConditionRendering,
    Lists
},
    data(){
      return{
        dummyDatas:[
           {name:'Akhil',specialized:"ECE",Designation:"React Developer",show:false},
           {name:'Alladi',specialized:"CSE",Designation:"Angular Developer",show:false},
           {name:'Kumar',specialized:"EEE",Designation:"Vue Developer",show:false},
           {name:'Akhil Alladi',specialized:"Mechanical",Designation:"Web Developer",show:false}],
           title:'Hello Everyone i am watching.......!',
           actressName:'Cameroon Diaz',actorName:'Tom Cruise',film:"Knight and Day",
           parentData:"Data From Parent Component",
           refData:"Parent Data",
           getData:"",
      }
    },
    provide(){
             return { myText:"Provide Data from Parent" }
           },
    mounted(){
          this.refData = this.$refs.child.yourPlace;
          console.log(this.$ref.child)
    },
    methods:{
         updateChild(parentData){
          this.parentData = parentData
         },
         getClickData(value){
                this.getData=value
         }
    }
    

}
</script>

<style scoped>
   span{
      font-weight: bold;
   }

   .propsPC, .eventCP, .eventBus, .provideInject, .refParentChild, .events, .directives, .conRend, .listsKeys{
      border: 2px solid black;
      padding: 10px;
      margin-top: 1rem;
      border-radius: 10px;
      
   }
   
</style> >