<template>
    <div class="container-fluid">
        <div class="row d-flex justify-content-center align-items-center m-4">
            <div class="col-12 col-md-8 col-lg-6 col-xl-5 ">
                <div class="card bg-primary text-white" style="border-radius: 1rem;">
                    <div class="card-body p-4 text-center d-flex flex-column justify-content-around" style="min-height: 80vh;">
                        <h5 class="text-white-50">Masukan Email atau ID Karyawan beserta password anda!</h5>
                        <form @submit.prevent="login">
                            <div class="form-outline form-white">
                                <input v-model="email" type="text" id="typeEmailX" class="form-control form-control-lg" />
                                <label class="form-label" for="typeEmailX" name="name">Email/ID Karyawan</label>
                            </div>
                            <div class="form-outline form-white">
                                <input v-model="password" type="password" id="typePasswordX" class="form-control form-control-lg" />
                                <label class="form-label" for="typePasswordX" name="pass">Password</label>
                            </div>
                            <button class="btn btn-outline-light btn-lg px-5" type="submit">Login</button>
                        </form>
                        <div class="row">
                            <div class="col-md-5 p-0">
                                <a href="#" class="text-white">Belum punya akun?</a>
                            </div>
                            <div class="col-md-2">
                                <p>•</p>
                            </div>
                            <div class="col-md-5 p-0">
                                <a href="#" class="text-white">Lupa password?</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
import { useRouter } from 'vue-router';


export default {
    
    data() {
        return {
            email: '',
            password: ''
        }
    },
    methods: {
        login: function() {
            var api_url = import.meta.env.VITE_API_URL
            var body, tipe_user;

            if ( this.isValidEmail(this.email)) {
                api_url = api_url + "/mentor/login/"
                tipe_user = "mentor"
                body = {
                        email: this.email,
                        password: this.password
                    }
            } else {
                api_url = api_url + "/admin/login/"
                tipe_user = "admin"
                body = {
                        id: this.email,
                        password: this.password
                    }
            }

            try {
                axios.post(api_url, body)
                .then(response => {
                    sessionStorage.setItem('access_token', response.data.access_token);
                    sessionStorage.setItem('user_type', tipe_user)
                    this.$router.push("/dashboard")
                })
                .catch(error => {
                    console.log(error);
                });
            } catch (error) {
                console.error(error);
                
            }
        },
        isValidEmail : function (email) {
            
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            return emailRegex.test(email);
        }
    }
}
</script>
