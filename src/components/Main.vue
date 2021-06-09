<template>
    <main>
        <div class="music" >
            <Card v-for="component,index in components" :key="index" :item="component" />
        </div>
    </main>
</template>

<script>
import Card from './Card';
import axios from 'axios';

export default {
    name: 'Main',
    components: {
        Card
    },
    data: function () {
        return {
            apiUrl : 'https://flynn.boolean.careers/exercises/api/array/music',
            components: []
        }
    },
    created: function () {
        axios
            .get(this.apiUrl)
            .then(
                (response) => {
                    console.log(this.components);
                    this.components = response.data.response;
                }
            )
    }

}
</script>

<style lang="scss" scoped>
    @import '../style/variables';

    main {
        height: 93vh;
        background-color: $backgroundColor;

    }
    .music {
        margin: 0 auto;
        max-width: 1170px;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
        align-content: center;
    }
</style>