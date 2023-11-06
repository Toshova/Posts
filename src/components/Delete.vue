<template>  
<div class="d-grid gap-2 d-md-flex justify-content-md-end">
        <button type="button"
        class="btn"  
         @click="$emit('remove-post', post.id)"><img src="./icons/trash3.svg">
        </button>
        </div>
</template>

<script>
export default {
    props: {
    post: {
        type: Object,
        required: true
        
    }
},
    
}
</script>

<style scoped>
.btn{
    float: right;
}
</style>