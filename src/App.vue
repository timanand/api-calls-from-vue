<template>
  <CreatePost />
  <UpdatePost />
  <DeletePost />
  <GetEmployees />
</template>

<script>
import GetEmployees from './components/GetEmployees.vue'
//import CreatePost from './components/CreatePost.vue'
//import UpdatePost from './components/UpdatePost.vue'
import DeletePost from './components/DeletePost.vue'



export default {
  name: 'App',
  components: {
    GetEmployees,
    //CreatePost,
    //UpdatePost,
    DeletePost,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
