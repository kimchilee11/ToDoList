<template>
    <div class="comp-tabs">
        <div class="tabs-title">
            <span>
                {{ title }}
            </span>
            
        </div>     
    </div>

</template>

<script>
export default {
    name: 'comp-tabs',
    // props: {
    //     title : String
    //     } ,
    data(){
        return{
            
        }
    }
}
</script>

<style>
    .tabs-title{
        border: 2px solid #000;
        padding: 20px;
        display: block;
        margin: 20px;
    }
</style>