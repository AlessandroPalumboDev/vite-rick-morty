<script>
import CharactersList from './AppCharactersList.vue';
import {store} from '../store.js';


export default {
    name: 'AppMain',

    components:{
        CharactersList,
    },

    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <CharactersList/>
</template>

<style>

</style>