<template>
    <main>
        <Card />
    </main>
</template>

<script>
import Card from './Card';

export default {
    name: 'Main',
    components: {
        Card
    }

}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';

    main {
        height: 93vh;
        background-color: $backgroundColor;
    }
</style>