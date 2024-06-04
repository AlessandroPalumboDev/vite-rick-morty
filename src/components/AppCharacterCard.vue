<script>
import {store} from '../store.js';
export default {
    name: 'AppCharacterCard',

    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <div class="container">
        <div class="row">
            <div class="col-25" v-for="result in store.results">
                <div class="card" >
                    <img :src="result.image" :alt="result.name">
                    <h3>{{ result.name }}</h3>
                    <div class="info">
                        <p>{{ result.status }}</p>
                        <p id="specie">{{ result.species }}</p>
                    </div>  
                </div>
            </div>
        </div>
    </div>
      

</template>

<style scoped lang="scss">
@use '../assets/scss/partials/variables';

.container{
    margin: 0 auto;
    max-width: 900px;

    .row{
        width: 100%;
        display: flex;
        flex-wrap: wrap;

        .col-25{
            width: calc(100% / 4 - 20px);
            margin-inline: 10px;

            .card{
                text-align: center;
                
                &:hover{
                    width: 110%;
                    margin: -20px -10px -1px -10px;
                }

                &:hover img{
                box-shadow: 0px 0px 35px 10px #000000;
                }

                img{
                    width: 100%;
                    border-radius: 50%;
                    margin: 10px 0;
                    object-fit: cover;
                    box-shadow:variables.$ombra-card;


                }

                .info{
                    margin: 20px 0;

                }

            }

        }
    }
}
    

</style>