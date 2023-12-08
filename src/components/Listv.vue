<template>
   

    <div v-for="pname of products" :key="pname.id">
            <Prodvi :pname="pname" />
    </div>

</template>

<script>
import Prodvi from './Prodvi.vue'

export default{
    name: 'Listv',
    props:{
        products: Array
    },
    components:{
        Prodvi
    }
}

</script>

<style>


</style>
