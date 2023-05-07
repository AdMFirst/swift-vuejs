<script setup>
import axios from 'axios';
import AdminSideBar from '../components/AdminSideBar.vue';
import MentorSideBar from '../components/MentorSideBar.vue';
import DashboardAdmin from '../components/DashboardAdmin.vue';
import DashboardMentor from '../components/DashboardMentor.vue';

var yourJWTToken = sessionStorage.getItem('access_token');
var user_type = sessionStorage.getItem("user_type");
var activeTab = 'tab1';

if (yourJWTToken == null) {
    window.location.href = '/login';
}

var yourConfig = {
   headers: {
      Authorization: "Bearer " + yourJWTToken
   }
}
if(user_type == "admin") {
    axios.get(import.meta.env.VITE_API_URL+"/admin/mydata/", yourConfig).catch(
        (error) => {
            console.log(error);
            alert("token expired, mohon masuk kembali")
            sessionStorage.clear()
            window.location.href = '/login';
        }
    )
} else {
    axios.get(import.meta.env.VITE_API_URL+"/mentor/mydata/", yourConfig).catch(
        (error) => {
            console.log(error);
            alert("token expired, mohon masuk kembali")
            sessionStorage.clear()
            window.location.href = '/login';
        }
    )
}

</script>

<template>
    <div class="container-fluid m-0 p-0 d-flex flex-direction-row" style="height: 90vh;">
        <AdminSideBar v-if="user_type === 'admin'" ></AdminSideBar>
        <MentorSideBar v-else-if="user_type === 'mentor'" ></MentorSideBar>
        <DashboardAdmin v-if="user_type === 'admin'"></DashboardAdmin>
        <DashboardMentor v-else-if="user_type === 'mentor'"/>
    </div> 

</template>

  