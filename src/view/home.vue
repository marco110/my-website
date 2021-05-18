<template>
    <div class="alert">
        <h2>更多内容,敬请期待...</h2>
        <div style="text-align: center">
            <video width="420" height="340" controls="controls">
                <source src="../assets/video/haha.mp4" type="video/mp4" />
            </video>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Home'
};
</script>

<style scoped>
h1 {
    text-align: center;
    margin: 0;
    padding: 0.6em 2em 0.4em;
    background-color: #00995d;
    color: #fff;
    font-weight: normal;
    font-size: 1.75em;
    border-bottom: 2px solid #000;
}

h1 strong {
    font-weight: bold;
    font-size: 1.5em;
}

h2 {
    text-align: center;
    background-color: #00995d;
    font-size: 1.1em;
    font-weight: bold;
    color: #fff;
    margin: 0;
    padding: 0.5em;
    border-bottom: 2px solid #000;
}

hr {
    display: none;
}

.alert {
    border: 2px solid #000;
}

video {
    max-width: 100%;
}

li {
    text-align: center;
}

img {
    width: 500px;
    height: 350px;
    border: 2px solid #fff;
    padding: 2px;
    margin: 0 auto;
}

li img:hover {
    transform: scale(1.2);
}

.logos {
    margin: 1em;
    text-align: center;
}

:link {
    color: #c00;
}

:visited {
    color: #c00;
}

a:hover {
    color: #f50;
}
</style>
