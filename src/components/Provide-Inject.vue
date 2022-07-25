<template>
         <div >
            <h1>Inject Data</h1>
            <p >{{myText}}</p>
            <button >Click</button>
         </div>
</template>

<script>
export default {
       name:'Provide-Inject',
       inject:['myText'],
};
</script>

<style>

</style>