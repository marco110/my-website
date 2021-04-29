<template>
    <div class="footer">
        <a style="color:#fff; vertical-align:middle;" href="http://marcoma.site/">marcoma.site</a>
        <span class="separator"></span>
        <a style="color:#fff; vertical-align:middle;" target="_blank" rel="noopener" href="http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=2021015312">鲁ICP备2021015312号</a>
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
    background-color: rgb(59, 60, 61);
}

.separator {
	border-right: 1px solid #efefef;
	border-left: 1px solid #efefef;
	margin: 0px 10px;
	height: 80px;
	font-size: inherit;
    vertical-align:middle;
}
</style>