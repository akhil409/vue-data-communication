<template>
        <div>
            {{msg}}
            <h1>{{msg}}</h1>
        </div>
</template>

<script>
export default {
       name:'Event-Bus2',
          mounted(){
            this.$root.$on('message',(msg)=>{
                console.log(msg)
                return msg;
            })
          },
}
</script>

<style>

</style>