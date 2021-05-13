<template>
    <div class="footer">
        <span style="color: #fff; vertical-align: middle">Copyright © 2021 Marco Ma All Rights Reserved</span>
        <span class="separator"></span>
        <a
            style="color: #fff; vertical-align: middle"
            target="_blank"
            href="http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=2021015312"
            >鲁ICP备2021015312号</a
        >
    </div>
</template>

<script>
export default {
    name: 'Footer'
};
</script>

<style scoped>
.footer {
    position: absolute;
    bottom: 0;
    width: 100%;
    padding: 10px 0;
    color: #ffffff;
    background-color: rgb(59, 60, 61);
}

.footer a {
    text-decoration: none;
}

.separator {
    border-right: 1px solid #efefef;
    border-left: 1px solid #efefef;
    margin: 0px 5px;
    height: 80px;
    font-size: inherit;
    vertical-align: middle;
}
</style>