<template>

    <div class="container vh-100 d-flex justify-content-center align-items-center">

        <div class="card shadow p-4" style="width:400px">

            <h3 class="text-center mb-4">
                User Guide Access
            </h3>

            <div class="mb-3">
                <input v-model="userId" type="text" class="form-control" placeholder="Enter Access ID" />
            </div>

            <button class="btn btn-primary w-100" @click="login">
                Login
            </button>

            <div v-if="error" class="text-danger mt-3 text-center">
                Invalid ID
            </div>

        </div>

    </div>

</template>

<script>
export default {

    data() {
        return {
            userId: '',
            error: false
        }
    },

    methods: {

        login() {

            const allowedIDs = ['ABC123', 'USER001', 'HIRAYA']

            if (allowedIDs.includes(this.userId)) {

                localStorage.setItem('access', 'true')

                this.$router.push('/dashboard')

            } else {

                this.error = true

            }

        }

    }

}
</script>