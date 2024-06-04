<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import Loader from './components/AppMainLoader.vue';

import axios from 'axios';
import {store} from './store';
export default{
  name: 'MyApp',

  components: {
    AppHeader,
    AppMain,
    Loader,
    // AppFooter
  },

  data(){
    return{
      store,
    };
  },

  methods:{
    searchCharacter(){
      store.loading = true;
    }
  },

  created() {
    axios.get(store.apiUrl).then((response) => {
      store.results = response.data.results;
      store.info = response.data.info;
      store.loading = false;
    });
    this.searchCharacter();
  },
};
</script>
<template>

  <header>
    <AppHeader />
  </header>

  <main>
    <Loader v-if="store.loading"/>
    <AppMain v-else/>
  </main>
  
</template>

<style scoped lang="scss">
header{
margin-bottom: 40px;
}


</style>
