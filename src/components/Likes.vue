<template>
<div class="containerBtn">
    
<button type="image"  class="btn img" @click="addLike"><img src="./icons/heart.svg"> {{ likes }}</button>
<button type="image" class="btn" @click="addDislike"><img src="./icons/hand-thumbs-down.svg"> {{ dislikes }}</button>
</div>
</template>

<script>
export default {
 data() {
return {
    likes: '',
    dislikes: ''
}
 },
 methods: {
    
    addLike(){
        this.likes=+(this.likes)+1
    },
    addDislike() {
        this.dislikes=+(this.dislikes)+1
    }
 }
}

</script>

<style scoped>

</style>