<script setup>
import LoginForm from "../components/LoginForm.vue"

const isLoggedIn = sessionStorage.getItem('isLoggedIn');

if (isLoggedIn) {
    window.location.href = '/dashboard';
}
</script>

<template>
    <div>
        <LoginForm v-if="!isLoggedIn" />
    </div>
</template>
