<script>
import ChararterCard from './AppCharacterCard.vue';

export default {
    name: 'AppCharactersList',

    components:{
        ChararterCard,
    }
}
</script>

<template>
    <div class="container">
        <div class="row">
            <div class="col-25">
                <ChararterCard />
            </div>
            <div class="col-100">
                <h5>N elementi trovati</h5>
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
                width: calc(100% / 4);

            }
            .col-100{
                width: 100%;

                h5{
                    font-weight: 800;
                    text-align: center;
                    margin-top: 20px;
                }
            }
        }
    }
</style>