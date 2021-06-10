<template>
    <div class="bar">
        <img src="../assets/spotify.png" alt="spotofy">
        <select name="genere" id="genere" v-model="selected" @change="$emit('gnrSelected', selected)">
            <option value="">Seleziona un genere</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'TopBar',
    data: function () {
        return {
            selected: ''
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';

    .bar {
        display: flex;
        justify-content: space-between;
        align-items: center;
        height: 7vh;
        padding: 0 30px;
        background-color: $mainColor;

        img {
            height: 80%;
        }

        select {
            padding: 5px 10px;
            border-radius: 5px;
            background-color: $backgroundColor;
            border-color: white;
            color: white;
        }
    }
</style>