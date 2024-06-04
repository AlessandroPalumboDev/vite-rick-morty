<script>
import CharacterCard from './AppCharacterCard.vue';
import {store} from '../store.js';

export default {
    name: 'AppCharactersList',

    components:{
        CharacterCard,
    },

    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <CharacterCard />
    <div class="col-100">
        <h5>Found {{ store.results.length }} characters </h5>
    </div>
</template>

<style scoped lang="scss">
    .col-100{
        width: 100%;

        h5{
            font-weight: 800;
            text-align: center;
            margin: 20px 0;
        }
    }
</style>