<template>
        <div class="container">
            <h1>Conditions in Vue.js</h1>
            <!-- v-if & v-else Directives -->
             <button v-on:click="error=!error" class="form-control btn btn-danger">Toggle Error</button>
             <button v-on:click="success=!success" class="form-control btn btn-success">Toggle Success</button>
             <p v-if="error">An Error has been Occur...! </p>
             <p v-else-if="success">Succeeded....!</p>  <br> <br>
            <!-- v-show & v-hide Directives -->
             <button v-on:click="loggedOut=!loggedOut" class="form-control btn btn-danger">Error occur while loggedIn</button>
             <button v-on:click="loggedIn=!loggedIn" class="form-control btn btn-success">LoggedIN Successfully</button>
             <p v-show="loggedOut">An Error has been Occur...! </p>
             <p v-show="loggedIn">Successfully Logged In....!</p>

             <!-- Login Form using conditional Rendering -->
             <div v-if="login">
                 <h2>You have successfully Logged in to your Account</h2>
             </div>
             <div v-else>
                <h2>Please Login to access your Account....!</h2>
             </div>
             <button v-on:click="login =!login" class="form-control btn btn-warning" id="conren">
                <p v-if="login" >Login</p>
                <p v-else>LogOut</p>
             </button>
        </div>
</template>

<script>
export default {
       name:'ConditionRendering',
       data(){
        return{
            error:false,
            success:false,
            loggedIn:false,
            loggedOut:false,
            login:false,
        }
       }
}
</script>

<style scoped>
      button, #conren{
        width: 20%;
        border-radius: 5px;
      }
</style>