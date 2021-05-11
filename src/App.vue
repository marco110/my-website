<template>
    <Home />
    <Footer />
</template>

<script>
import Home from './view/home';
import Footer from './components/Footer';

export default {
    name: 'App',
    components: {
        Home,
        Footer
    }
};
</script>

<style>
* {
    margin: 0;
    padding: 0;
    font-size: 14px;
}

#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}
</style>
