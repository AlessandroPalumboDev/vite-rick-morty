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
<div class="container">
    <CharacterCard />
    <div class="col-100">
        <h5>Found {{ store.results.length }} characters of {{ store.info.count }}</h5>
    </div>
        <a id="prev" :href="store.info.prev">
            <button>< PREV</button>
        </a>
        <a id="next" :href="store.info.next">
            <button>NEXT ></button>
        </a>
    </div>
</template>

<style scoped lang="scss">
@use '../assets/scss/partials/variables';

.container{
    position: relative;
}

    .col-100{
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 40px;
        position: relative;

        h5{
            font-weight: 800;
            margin: 10px auto;
        }

    }

    button{
            font-weight: 600;
            padding: 30px 14px;
            border: none;
            border-radius: 50%;
            margin-inline: 20px;
            background-color: rgb(0, 255, 64);
            box-shadow: variables.$ombra-sfera;
            color: black;

            &:hover{
                cursor: pointer;
                color: white;
                border: none;
                box-shadow: inset 0px 0px 50px -10px #000000,0px 0px 10px 0px #000000;
            }
        }

    #prev, #next{
        position: absolute;
        top: calc(50% - 100px);
        z-index: 1;
    }

    #next{
        right: 0 ;
    }
</style>