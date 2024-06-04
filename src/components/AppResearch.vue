<script>
import { store } from '../store';
export default {
    name: 'AppResearch',
    data(){
        return{
            store,
        };
    },

    methods:{
        search(){
            console.log('ricerca in corso');
        },
    }
}
</script>

<template>
    <div class="character-search">
    <input type="text" placeholder="Search character">

    <select name="Search" id="select" @change="search" v-model="store.searchKey">
        <option value="0">Select status</option>
        <option value="alive">Alive</option>
        <option value="dead">Dead</option>
        <option value="unknow">Unknow</option>
    </select>

    <button id="search">Search</button>
    <button id="reset">Reset</button>
</div>
</template>

<style scoped lang="scss">
@use '../assets/scss/partials/variables';
.character-search{
    text-align: center;

    button, select, input{
        padding: 10px;
        border: 1px solid lightgray;
        border-radius: 10px;
        margin-inline: 10px;

    }
    #reset{
        background-color: orange;
        &:hover{
            background-color: rgb(212, 138, 0);
            box-shadow:variables.$ombra-bottone;
            color: white;
            cursor: pointer;  
        }
    }
    #search{
        background-color: rgb(1, 106, 243);
        color: white;

        &:hover{
            background-color: rgb(2, 73, 165);
            box-shadow:variables.$ombra-bottone;
            cursor: pointer;
        }
    }

}
</style>