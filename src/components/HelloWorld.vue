<template>
    <div class="hello" style="width: 100%;height: 100%;">
        <div id="map" style="width: 100%;height: 100%;background: bisque">dasdsa</div>
    </div>
</template>

<script>
    import * as Cesium from 'cesium/Cesium'
    import * as widgets from "cesium/Widgets/widgets.css"

    export default {
        name: 'HelloWorld',
        props: {
            msg: String
        },
        mounted() {
            this.init();
        },
        methods: {
            init() {
                let viewerOption = {
                    geocoder: false, // 地理位置查询定位控件
                    homeButton: false, // 默认相机位置控件
                    timeline: false, // 时间滚动条控件
                    navigationHelpButton: false, // 默认的相机控制提示控件
                    fullscreenButton: false, // 全屏控件
                    scene3DOnly: true, // 每个几何实例仅以3D渲染以节省GPU内存
                    baseLayerPicker: false, // 底图切换控件
                    animation: false // 控制场景动画的播放速度控件
                };
                let viewer = new Cesium.Viewer('map', viewerOption);
                viewer._cesiumWidget._creditContainer.style.display = "none";// 隐藏版权
            }
        }
    }
</script>

<style scoped lang="less">
</style>
