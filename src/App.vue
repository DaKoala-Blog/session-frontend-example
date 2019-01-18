<template>
    <div id="app">
        <h1>Time: {{time}}</h1>
    </div>
</template>

<script>
    import axios from 'axios';
    axios.defaults.withCredentials = true;

    export default {
        name: 'app',
        data() {
            return {
                time: null,
            }
        },
        created() {
            axios.get('http://localhost:3000/time')
                .then((res) => {
                    this.time = res.data;
                });
        }
    };
</script>

<style>

</style>
