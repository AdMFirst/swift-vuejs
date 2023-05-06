<script setup>
import LoginForm from "../components/LoginForm.vue"

const isLoggedIn = sessionStorage.getItem('access_token');

if (isLoggedIn) {
    window.location.href = '/dashboard';
}
</script>

<template>
    <div>
        <LoginForm v-if="!isLoggedIn" />
    </div>
</template>
