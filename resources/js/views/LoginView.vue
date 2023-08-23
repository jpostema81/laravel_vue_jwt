<script setup>
import axios from "axios";
import { ref } from "vue";

const credentials = ref({ email: "", password: "" });
const loginMessage = ref("");

const login = async () => {
    try {
        const { data } = await axios.post("api/login", credentials.value);
        loginMessage.value =
            "Je bent ingelogd met JWT. Inhoud JWT token: " + data.access_token;
    } catch {
        loginMessage.value = "Inloggen met JWT mislukt";
    }
};
</script>

<template>
    <div>
        <h1>Login page</h1>

        <div>{{ loginMessage }}</div>

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
