<template>
    <div>
        <form @submit.prevent="deletePost">

            <div>
                <label for="id">Post Id</label>
                <input type="text" id="id" v-model="formData.Id">
            </div>

            <div>
                <label for="firstName">Post First Name</label>
                <input type="text" id="firstName" v-model="formData.FirstName">
            </div>
            <div>
                <label for="lastName">Post Last Name</label>
                <input type="text" id="lastName" v-model="formData.LastName">
            </div>
            <div>
                <label for="title">Post Title</label>
                <input type="text" id="title" v-model="formData.Title">
            </div> 

            <button>Delete Post</button>

        </form>

    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        name: 'DeletePost',
        data() {
            return {
                formData : {
                    Id: '',
                    FirstName: '',
                    LastName: '',
                    Title: '',
                },
            }
        },
        methods: {
            deletePost() {
                axios.delete('https://localhost:44351/api/staffmembers/delete/11')
                .then(response => console.log(response))
                .catch(error => console.log(error))
            }
        }
    }
</script>

<style scoped>

</style>