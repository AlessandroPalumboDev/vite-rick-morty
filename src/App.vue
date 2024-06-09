<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import Loader from './components/AppMainLoader.vue';
import AppResearch from './components/AppResearch.vue';


import axios from 'axios';
import {store} from './store';
export default{
  name: 'MyApp',

  components: {
    AppHeader,
    AppMain,
    Loader,
    AppResearch,
    // AppFooter
  },

  data(){
    return{
      store,
    };
  },

  methods:{
    searchCharacter(){
      // store.loading = true;
      const params = {};
      params.name = this.store.searchName
      params.status = this.store.searchKey;
      axios.get(store.apiUrl , {params}).then((response) => {
      this.store.results = response.data.results;
      // this.store.info = response.data.info;
    })},

    reset(){
      this.store.searchKey = '';
      this.store.searchName = '';
      this.searchCharacter();
    }
  

  },

  created() {
    this.searchCharacter()
  }
    
  
  }
</script>
<template>

  <header>
    <AppHeader />
    <AppResearch @cerca="searchCharacter" @reset="reset"/>
  </header>

  <main>
    <!-- <Loader v-if="store.loading"/> -->
    <AppMain />
  </main>
  
</template>

<style scoped lang="scss">
header{
margin-bottom: 40px;
}


</style>
