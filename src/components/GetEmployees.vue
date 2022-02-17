<template>
    <div>
        <button @click="GetEmployees">Load Posts</button>
        <div v-for="post in posts" :key="post.id">
            <h3>{{post.Id}} {{post.Title}} {{post.FirstName}} {{post.LastName}}</h3>
            <p>{{post.body}}</p>
            <hr />
        </div>    
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        name: 'GetEmployees',
        data() {
            return {
                posts: [],
            }
        },
        methods: {
            GetEmployees() {
                axios.get('https://localhost:44351/api/StaffMembers')
                .then((response) => {
                    console.log(response.data)
                    this.posts = response.data
                })
                .catch(error => {
                    console.log(error)
                })
            }
        }
        
    }
</script>

<style scoped>

</style>