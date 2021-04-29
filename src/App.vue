<template>
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to my website......" />
    <Footer />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import Footer from './components/Footer';

export default {
    name: 'App',
    components: {
        HelloWorld,
        Footer
    }
};
</script>

<style>
* {
margin: 0;
padding: 0;
}

#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
