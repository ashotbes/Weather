<template>
    <div id="app" :class="typeof weather.main != 'undefined' && weather.main.temp > 16 ? 'warm' : ''">
        <main>
            <Search/>
        </main>
    </div>
</template>

<script>
import Search from "@/components/Search.vue";

export default {
    name: 'app',
    components: {Search},
    data() {
        return {
            api_key: '0c76a4d7be44b4bc3ce3f41e3a9ec018',
            url_base: 'https://api.openweathermap.org/data/2.5/',
            query: '',
            weather: {}
        }
    },
    methods: {
        }
    }

</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'montserrat', sans-serif;
}

#app {
    background-image: url('./assets/cold-bg.jpg');
    background-size: cover;
    background-position: bottom;
    transition: 0.4s;
}

#app.warm {
    background-image: url('./assets/warm-bg.jpg');
}

main {
    min-height: 100vh;
    padding: 25px;

    background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.25), rgba(0, 0, 0, 0.75));
}


</style>