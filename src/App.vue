<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from 'axios';
import {store} from './store';
export default{
  name: 'MyApp',

  components: {
    AppHeader,
    AppMain,
    // AppFooter
  },

  data(){
    return{
      store,
    };
  },

  created() {
    axios.get(store.apiUrl).then((response) => {
      store.results = response.data.results;
    });
  },
};
</script>
<template>

  <header>
    <AppHeader />
  </header>

  <main>
    <AppMain />
  </main>
  
</template>
<!-- <style></style> -->
