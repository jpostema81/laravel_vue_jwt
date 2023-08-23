<script setup>
import axios from "axios";
const login = () => {
    axios.post("api/login", { email: "test@test.com", password: "" });
};
</script>

<template>
    <div class="about">
        <h1>This is the login page</h1>

        <button type="button" @click="login()">Login</button>
    </div>
</template>

<style>
@media (min-width: 1024px) {
    .about {
        min-height: 100vh;
        display: flex;
        align-items: center;
    }
}
</style>
