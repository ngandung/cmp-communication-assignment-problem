<template>
    <form @submit.prevent="addNewUser">
        <div>
            <label>Username</label>
            <input type="text" v-model="inputUsername">
        </div>
        <div>
            <label>Age</label>
            <input type="number" v-model="inputAge">
        </div>
        <button>Add User</button>
    </form>
    
</template>

<script>
    export default {
        data() {
            return {
                inputUsername: '',
                inputAge: ''
            };
        },
        emits: ['add-user'],
        methods: {
            addNewUser() {
                this.$emit('add-user', this.inputUsername, this.inputAge);
                this.inputUsername = '';
                this.inputAge = '';
            }
        }
    };
</script>