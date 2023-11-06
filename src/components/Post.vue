<template>

<div class="accordion" id="accordionExample" v-for="post in posts">
  <div class="accordion-item">
    <h2 class="accordion-header">
      <button
      @click="post.expanded = !post.expanded" 
      class="accordion-button" 
      type="button" 
      data-bs-toggle="collapse" 
      data-bs-target="#collapseOne" 
      aria-expanded="false" 
      aria-controls="collapseOne">
       <Date/>
      </button>
    </h2>
    <div  
    :class="{hidden: post.expanded}"
    id="collapseOne" 
    class="accordion-collapse collapse show"    
    data-bs-parent="#accordionExample"
    >
      <div class="accordion-body" >
        {{ post.body }}     
        
        </div>
        <div class="containerBtn">
        <Likes/>
        <Delete
        :post="post"
        @remove-post="removePost"/>
        </div>
        
      </div>
      
      
    </div>
    
  
  
  
</div>

</template>

<script>    
import Likes from './Likes.vue' 
import Date from './Date.vue'
import Delete from './Delete.vue'

export default {
    props: {
        posts: {
            type: Array,
            required: true
        }
    },

methods:{
    removePost(id){
        this.$emit('remove-post', id)
    }
},

components: {
    Likes, Date, Delete
}

}
</script>

<style scoped>
.btn btn-outline-primary {
    margin: 0
}
.hidden {
    display: none;
}

</style>