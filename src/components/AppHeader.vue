<script>
import AppResearch from './AppResearch.vue';
export default {
    name: 'AppHeader',

    components:{
        AppResearch,
    },
};
</script>
<template>
    <h1>Rick and Morty App</h1>
    <AppResearch />
</template>

<style scoped lang="scss">
h1 {
  text-align: center;
  font-weight: 900;
  margin: 20px 0 40px 0;
}

</style>