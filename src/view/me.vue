<template>
    <div class="main">
        <div class="item-wrap">
            <!-- 商品预览 -->
            <div class="preview-wrap">
                <div class="preview">
                    <img :alt="goodsImgs[currentGoodsImgIndex].src" />
                </div>

                <div class="preview-thumb-wrap">
                    <div class="preview-thumb" v-for="(item, index) in goodsImgs" :key="index" @mouseover="showCurrentImg(index)">
                        <img :alt="item.src" />
                    </div>
                </div>
            </div>

            <!-- 商品信息 -->
            <div class="itemInfo-wrap">
                <div class="sku-name">商品名称XXXXXXXXXXX</div>
                <div>红色小字介绍</div>
                <div>
                    <div>
                        <span>价格</span> <span> ￥14000</span>
                        <div style="display: inline">
                            <div>累计评价</div>
                            <div>6</div>
                        </div>
                    </div>
                    <div><span>促 销</span> <span> ￥14000</span></div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Me',
    data() {
        return {
            currentGoodsImgIndex: 0,
            goodsImgs: [{ src: '1' }, { src: '2' }, { src: '3' }]
        };
    },
    methods: {
        showCurrentImg(index) {
            this.currentGoodsImgIndex = index;
        }
    }
};
</script>

<style lang="less" scoped>
.item-wrap {
    display: flex;
    flex-direction: row;

    .preview-wrap {
        width: 400px;

        .preview {
            width: 100%;
            height: 400px;
            border: 1px solid #f1f1f1;
        }

        .preview-thumb-wrap {
            width: 100%;
            margin: 20px 0;

            .preview-thumb {
                display: inline-block;
                width: 60px;
                height: 60px;
            }
        }
    }

    .itemInfo-wrap {
        flex: 1;
        padding: 0 20px;

        div {
            text-align: left;
        }

        .sku-name {
            font: 700 16px Arial, 'microsoft yahei';
            color: #666;
        }
    }
}
</style>
