<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
export default{
  name: 'MyApp',

  components: {
    AppHeader,
    AppMain,
    // AppFooter,
  }
}
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
