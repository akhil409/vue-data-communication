<template>
    <div>
        <button v-on:click="sendMessage" class="form-control btn btn-secondary">
            <router-link to="/Event-Bus2">Click Me</router-link>
        </button>
    </div>
</template>

<script>
export default {
       name:'Event-Bus1',
       methods:{
            sendMessage(){
                this.$root.$emit('message',"Message from Alexa..!")
            },
       },
}
</script>

<style>

</style>