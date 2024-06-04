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
        }
    }
</style>