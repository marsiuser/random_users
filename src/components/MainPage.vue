<template>
  <div>
      <div class="page-container">
        <Header />
        <md-app>
            <md-app-toolbar>
              <span class="md-title">Detailed user information</span>
            </md-app-toolbar>
               <md-app-drawer md-permanent="full">
                  <UserList @viewDetails="viewDetails" />
               </md-app-drawer>
            <md-app-content>
              <DetailsInfo :user="selectedProduct" />
            </md-app-content>
        </md-app>
      </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      selectedProduct: {}
    }
  },
  components: { 
      Header: () => import('./Header'),
      UserList: () => import('./UserList'),
      DetailsInfo: () => import('./DetailsInfo')
  },
  methods:{
    viewDetails(user){
      this.selectedProduct = user;
    }
  }
}
</script>

<style lang="scss">
  .md-card-header{
    text-align: center;
  }
</style>