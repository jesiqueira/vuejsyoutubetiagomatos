<template>
    <!-- <pre>{{ $route }}</pre> -->
    <!-- {{ $route.query.page }} -->
    Usuarios <br />
    <button @click="login()">Login</button>
</template>

<script>
export default {
    created() {
        // console.log(this.$route);
        console.log(this.$router);
    },
    methods: {
        login() {
            console.log('chamou!');
            this.$router.push({ name: 'about' });
        },
    },
};
</script>

<style></style>
