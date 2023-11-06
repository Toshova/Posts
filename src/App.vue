<template>
  <div class="container">
    <h1>My posts</h1>  
  <PostForm 
  @make-post="makePost" 
  />
  <Post
  @remove-post="removePost"
  :posts="posts" 
  />
  </div>

</template>


<script >
import Post from './components/Post.vue'
import PostForm from './components/PostForm.vue'
import Delete from './components/Delete.vue'

export default {
  data() {
    return {
        posts: [
              
        ],
    }
},
components: {
  Post, PostForm, Delete
},
methods: {
    
    makePost(post){
      this.posts.push(post)
    },
    removePost(id){
      let conf = confirm("Do U really want to delete it?")
      if(conf) {
        this.posts=this.posts.filter(t => t.id !== id)
      } else {
        this.posts
      }
           
    }
}
   
}

</script>

<style>
body {
  background: #ffffff;
background: linear-gradient(159deg,#ffffff 0%, #eaebeb 71%);
background: -webkit-linear-gradient(159deg,#ffffff 0%, #eaebeb 71%);
background: -moz-linear-gradient(159deg,#ffffff 0%, #eaebeb 71%);
}
h1 {
  margin-bottom: 2%;
  margin-top: 2%;
}
button {
  min-width: 70px;
  padding: 10px 14px;
  margin-top: 0.5%;
  margin-right: 0.5%;

}
.btn {
  border:0;
  
  
}
.containerBtn {
    display: flex;
    justify-content: flex-end;
    margin: 0;
    padding: 0;
    
}

</style>
