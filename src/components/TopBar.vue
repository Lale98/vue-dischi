<template>
    <div class="bar">
        <img src="../assets/spotify.png" alt="spotofy">
    </div>
</template>

<script>
export default {
    name: ' TopBar',

}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';

    .bar {
        display: flex;
        align-items: center;
        height: 7vh;
        background-color: $mainColor;

        img {
            margin-left: 30px;
            height: 80%;
        }
    }
</style>