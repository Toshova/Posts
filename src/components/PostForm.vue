<template>
<form  @submit.prevent>
    <div>
    <input class="d-inline-flex focus-ring py-1 px-2 text-decoration-none border rounded-2"    
    v-model="body" 
    @keypress.enter="makePost" 
    type="text" 
    placeholder="NamePost"
    >
    <div class="d-grid gap-2 d-md-flex justify-content-md-end">
        <button type="button"
         class="btn btn-outline-primary" 
         @click="makePost" 
         >
         Add it
        </button>
    </div>
</div>
    
  </form>

  
</template>

 
<script>


export default {
data(){
    return {
        body: ''
    }
},


methods: {

makePost(){
    if (this.body.trim()) {
        const newPost = {
            id:Date.now(),
            body: this.body,
            expanded: false,
        }
        this.$emit('make-post', newPost)
        this.body= ''
    }
}
}
}


</script>

<style scoped>
input {
    width: 100%;
    height: 50px;
}
form {
    margin-bottom: 5%;
}


</style>