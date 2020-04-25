<template>
  <div>
      <div class="page-container">
        <Header />
        <md-app>
            <md-app-toolbar>
              <span class="md-title">Detailed user information</span>
            </md-app-toolbar>
            <md-app-content>
              <AllUsers />
              <DetailsInfo />
            </md-app-content>
        </md-app>
      </div>
  </div>
</template>

<script>
export default {
  components: { 
      Header: () => import('./Header'),
      AllUsers: () => import('./AllUsers'),
      DetailsInfo: () => import('./DetailsInfo')
  }
}
</script>

<style lang="scss">
  .md-card-header{
    text-align: center;
  }
</style>