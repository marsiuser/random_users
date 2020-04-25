<template>
<md-app-drawer md-permanent="full">
     <div class="wrapper">
            <md-card class="list-cart">
          <md-card-header>
                <div class="md-title"><p>{{ user_info.name.first }} {{ user_info.name.last }}</p></div>
          </md-card-header>
          <md-card-content>
            <avatar :image="user_info.picture.medium" :size="80"/>
            <div class="user-id">
                <p><span>ID: </span> {{ user_info.id.value }}</p>
            </div>
          </md-card-content>
      </md-card>
      </div>
    </md-app-drawer>
</template>
<script>
import Avatar from 'vue-avatar-component'
export default {
    components:{
        Avatar
    },
  props:{
    user_info: {
      type: Object,
      default(){
        return {}
      }
    }
  },
  data(){
    return{}
  }
}
</script>

<style lang="scss">
.list-cart .md-card-header,
.md-card-content:last-of-type{
    padding: 0px;
}

</style>