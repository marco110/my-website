<template>
    <Header />
    <Home />
    <!-- <Me /> -->
    <Footer />
</template>

<script>
import Header from './components/header';
import Home from './view/home';
// import Me from './view/me';
import Footer from './components/footer';

export default {
    name: 'App',
    components: {
        Header,
        Home,
        Footer
        // Me
    }
};
</script>

<style lang="less">
@import url('./assets/css/global.less');

#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}
</style>
