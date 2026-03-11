<template>

    <div class="container vh-100 d-flex justify-content-center align-items-center">

        <div class="card shadow p-4" style="width:400px">

            <h3 class="text-center mb-4">
                User Guide
            </h3>

            <div class="mb-3">
                <input v-model="userId" type="text" class="form-control"
                    placeholder="Enter Your Application ID ex. 2083265" />
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

        async login() {

            this.error = false

            const scriptURL = "https://script.google.com/macros/s/AKfycbzJpVAvjbwWUKmE_HwVap-1AJJUk0XMrUSu1GdJGPLBMjsVk_30JFzeRRusp7dvEiEf-Q/exec"

            try {

                const response = await fetch(`${scriptURL}?id=${this.userId}&callback=?`)

                const data = await response.json()

                if (data.valid) {

                    localStorage.setItem('access', 'true')
                    this.$router.push('/dashboard')

                } else {

                    this.error = true

                }

            } catch (err) {

                console.error(err)
                this.error = true

            }

        }

    }

}
</script>