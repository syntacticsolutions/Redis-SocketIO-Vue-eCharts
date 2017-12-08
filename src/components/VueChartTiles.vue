<template>
    <div class="app-container">
        <ChartTile></ChartTile>
    </div>
</template>

<script>

import ChartTile from './ChartTile.vue'

export default {
    components: {
        ChartTile
    }
}
</script>

<style lang="scss" scoped>
    .app-container {
        position: absolute;
        top:0;
        left: 0;
        width:100%;
        height:100%;
    }
</style>

    