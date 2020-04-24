<template>
  <div>
      <div class="page-container">
        <Header />
        <md-app>
            <md-app-toolbar class="md-primary">
              <span class="md-title">Detailed user information</span>
            </md-app-toolbar>
            <md-app-drawer md-permanent="full">
              <AllUsers />
            </md-app-drawer>
            <md-app-content>
                <Details />
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
      Details: () => import('./Details')
  }
}
</script>

<style lang="scss">
  .md-card-header{
    text-align: center;
  }
</style>
