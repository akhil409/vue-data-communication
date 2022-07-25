<template>

      <div class="container" >    
                 <h1>Child Component</h1>
          <ul id="prop">
            <li v-for="dummyData in dummyDatas" v-bind:key="dummyData" v-on:click="dummyData.show = !dummyData.show">
                <p>Hi this is <span class="content">{{ dummyData.name }}</span> I am specialised in <span class="content">{{dummyData.specialized}}</span> and to know my current designation just click on the content.</p>
                <p v-show="dummyData.show"><span class="content">{{ dummyData.Designation }}</span ></p>
            </li>
          </ul>
<!-- Static Data Passing -->
          <ul>
             I have saw a film called <span class="content">{{film}}</span > and the actors are <span class="content">{{actressName}}</span> & <span class="content">{{actorName}}</span>. 
          </ul>
      </div>
</template>

<script>
export default {
    name:'PropsParentToChild',
    props:['dummyDatas','actressName','actorName','film'],
    data(){
        return{

        }
    }

}
</script>

<style scoped>
    ul{
        list-style-type: none;
    }
    #prop{
        border: 2px solid greenyellow;
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 2rem;
    }

    .content{
        font-weight: bold;
    }
   
</style>