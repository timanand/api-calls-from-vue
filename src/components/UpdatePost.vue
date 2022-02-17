<template>
    <div>
        <form @submit.prevent="updatePost">

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

            <button>Update Post</button>

        </form>

    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        name: 'UpdatePost',
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
            updatePost() {
                axios.put('https://localhost:44351/api/staffmembers/update/45', this.formData)
                .then(response => console.log(response))
                .catch(error => console.log(error))
            }
        }
    }
</script>

<style scoped>

</style>