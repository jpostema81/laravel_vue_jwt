<script setup>
defineProps({
    msg: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <div class="greetings">
        <h1 class="green">{{ msg }}</h1>
        <h3>
            Example project for testing

            <a
                href="https://jwt-auth.readthedocs.io/en/develop/"
                target="_blank"
                rel="noopener"
                >JWT</a
            >
            with

            <a
                href="https://laravel.com/docs/10.x"
                target="_blank"
                rel="noopener"
                >Laravel</a
            >
            +
            <a href="https://vitejs.dev/" target="_blank" rel="noopener"
                >Vite</a
            >
            +
            <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a
            >.
        </h3>
    </div>
</template>

<style scoped>
h1 {
    font-weight: 500;
    font-size: 2.6rem;
    position: relative;
    top: -10px;
}

h3 {
    font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
    text-align: center;
}

@media (min-width: 1024px) {
    .greetings h1,
    .greetings h3 {
        text-align: left;
    }
}
</style>
