<template>
   

    <div v-for="pname of products" :key="pname.id">
            <prodview :pname=pname />
    </div>

</template>

<script>
import prodview from './prodview.vue'

export default{
    name: 'Listv',
    props:{
        products: Array
    },
    components:{
        prodview
    }
}

</script>

<style>


</style>