<template>
    <main>
        <TopBar @gnrSelected="filterGen" />
        <div class="music" >
            <Card v-for="component,index in genereSelected" :key="index" :item="component" />
        </div>
    </main>
</template>

<script>
import Card from './Card';
import TopBar from './TopBar';
import axios from 'axios';

export default {
    name: 'Main',
    components: {
        Card,
        TopBar
    },
    data: function () {
        return {
            apiUrl : 'https://flynn.boolean.careers/exercises/api/array/music',
            components: [],
            genere: ''
        }
    },
    computed: {
        genereSelected : function () {
            const newArray = this.components.filter(
                (element) => {
                    if (this.genere == element.genre) {
                        return element
                    } else if (this.genere == '') {
                        return element
                    }
                }
            )
            return newArray;
        }
    },
    methods : {
        filterGen : function (gnr) {
            this.genere = gnr.trim();
        }
    },
    created: function () {
        axios
            .get(this.apiUrl)
            .then(
                (response) => {
                    this.components = response.data.response;
                }
            )
    }

}
</script>

<style lang="scss" scoped>
    @import '../style/variables';

    main {
        height: 100vh;
        background-color: $backgroundColor;

    }
    .music {
        margin: 0 auto;
        max-width: 1170px;
        height: 93vh;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
        align-content: center;
    }
</style>