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
                        <p>{{ result.species }}</p>
                    </div>  
                </div>
            </div>
        </div>
    </div>
      

</template>

<style scoped lang="scss">

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
                img{
                    width: 100%;
                    border-radius: 50%;
                    margin: 10px 0;
                    object-fit: cover;
                }

                .info{
                    margin: 20px 0;
                }

            }
        }
    }
}
    

</style>