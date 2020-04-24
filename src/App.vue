<template>
  <div id="app">
      <MainPage/>
  </div>
</template>

<script>
export default {
  name: 'app',
  components: {
    MainPage: () => import('./components/MainPage.vue')
  }
}
</script>


