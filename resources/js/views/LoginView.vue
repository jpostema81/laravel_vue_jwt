<script setup>
import axios from "axios";
import { ref } from "vue";

const credentials = { email: "", password: "" };

const login = () => {
    axios.post("api/login", credentials);
};
</script>

<template>
    <div>
        <h1>Login page</h1>

        <div id="form">
            <form @submit.prevent="login">
                <label for="email">Email</label>
                <input
                    id="email"
                    v-model="credentials.email"
                    placeholder="username"
                />
                <label for="password">Password</label>&nbsp;
                <input
                    id="password"
                    v-model="credentials.password"
                    placeholder="password"
                    type="password"
                />
                <input type="submit" value="log in" />
            </form>
        </div>
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

div#form label,
div#form input {
    outline: none;
    width: 100%;
}
</style>
