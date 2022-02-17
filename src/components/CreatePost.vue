<template>
    <div>
        <form @submit.prevent="createPost">
            <div>
                <label for="firstName">Post First Name</label>
                <input type="text" id="firstName" v-model="formData.firstName">
            </div>
            <div>
                <label for="lastName">Post Last Name</label>
                <input type="text" id="lastName" v-model="formData.lastName">
            </div>
            <div>
                <label for="title">Post Title</label>
                <input type="text" id="title" v-model="formData.title">
            </div>

            <button>Create Post</button>

        </form>

    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        name: 'CreatePost',
        data() {
            return {
                formData : {
                    firstName: '',
                    lastName: '',
                    title: '',
                },
            }
        },
        methods: {
            createPost() {
                axios.post('https://localhost:44351/api/staffmembers/create', this.formData)
                .then(response => console.log(response))
                .catch(error => console.log(error))
            }
        }
    }
</script>

<style scoped>

</style>