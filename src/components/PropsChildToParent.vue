<template>
      <button v-on:click="updateChildData" class="form-control btn btn-success">Click to change the Data</button>
</template>

<script>
export default {
    name:'PropsChildToParent',
    dat(){
        return{
            dupDatas:[
           {name:'Akhil',specialized:"ECE",Designation:"React Developer",show:false},
           {name:'Kittu',specialized:"CSE",Designation:"UI Developer",show:false},
           {name:'Mary',specialized:"B.Pharmacy",Designation:"System Engineer",show:false},
           {name:'Prakash',specialized:"Mechanical",Designation:"Tech Support",show:false}],
           title:'Data from Child Component',
        }
    },
    methods:{
        updateChildData(){
              this.$emit('changeData',"Data From Child Component")
        }
    }
    
}
</script>

<style scoped>

</style>