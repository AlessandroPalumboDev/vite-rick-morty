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
    <div class="col-100 absolute">
        <a :href="store.info.prev">
            <button>< PREV</button>
        </a>
        <a :href="store.info.next">
            <button>NEXT ></button>
        </a>
    </div>
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


        h5{
            font-weight: 800;
            margin: 10px auto;
        }

        button{
            font-weight: 600;
            padding: 30px 14px;
            border: 1px solid lightgray;
            border-radius: 50%;
            margin-inline: 20px;
            background-color: rgb(0, 255, 64);
            box-shadow:variables.$ombra-card;
            color: black;

            &:hover{
                background-color: rgb(0, 148, 37);
                cursor: pointer;
                color: white;
                box-shadow: inset 0px 0px 28px -4px #FFFFFF,0px 0px 30px 4px #000000;
            }
        }
    }

    .absolute{
        position: absolute;
        top: 50vh;
        z-index: 1;
        
    }
</style>