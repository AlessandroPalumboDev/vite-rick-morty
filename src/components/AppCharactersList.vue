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
        <h5>Found {{ store.results.length }} characters of {{ store.info.count }}</h5>
    </div>
    <div class="col-100">
        <a :href="store.info.prev">
            <botton>< PREV</botton>
        </a>
        <a :href="store.info.next">
            <botton>NEXT ></botton>
        </a>
    </div>
</template>

<style scoped lang="scss">
@use '../assets/scss/partials/variables';

    .col-100{
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;


        h5{
            font-weight: 800;
            margin: 10px auto;
        }

        botton{
            padding: 10px;
            border: 1px solid lightgray;
            border-radius: 10px;
            margin-inline: 10px;
            background-color: rgb(0, 255, 64);
            color: black;
            &:hover{
                background-color: rgb(2, 148, 38);
                box-shadow:variables.$ombra-bottone;
                cursor: pointer;
                color: white;
                
            }
        }
    }
</style>