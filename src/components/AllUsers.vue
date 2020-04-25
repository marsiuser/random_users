<template>
    <div class="wrapper">
    <md-toolbar class="md-transparent" md-elevation="0">
        Users list:
    </md-toolbar>
    <div class="user-list" v-for="(user, index) in users" :key="index">
          <div class="help_wrap">
            <ListUsers v-bind:user_info="user" />
            <md-card-actions>
                  <md-button @click="show(user.id.value)">Show info</md-button>
            </md-card-actions>
          </div>
          <md-app-content class="md-primary">
            <div class="add-info"  v-if="visible && currentId===user.id.value" :key="index">
                <DetailsInfo v-bind:user_data="user" />
            </div>
          </md-app-content>
        </div>
    </div>
</template>

<script>
import Avatar from 'vue-avatar-component'
export default {
  components: { 
   Avatar,
    DetailsInfo: () => import('./DetailsInfo'),
      ListUsers: () => import('./ListUsers')
  },
  props:{},
  data () {
    return {
      users: {},
      visible : false,
      currentId: ''
    }
  },
  mounted () {
    fetch('https://randomuser.me/api/?results=20&nat=us')
    .then((response) => {
      return response.json()
    })
    .then((data) => {
      this.users = data.results
    })
  },
  methods:{
    show(id){
      this.visible = !this.visible;
      this.currentId = id;
    },
  }
}
</script>

<style lang="scss">
.avatar[data-v-4ffd1741]{
    width: 50px !important;
    height: 50px !important;
}
.md-drawer.md-permanent{
    width: 220px;
}
.add-info{
    padding: 10px;
}
.md-card-actions.md-alignment-right{
    justify-content: flex-start;
}
.md-app{
    padding: 0px 30px;
}
.md-card-header{
    padding: 10px;
}
.md-title p{
    font-size: 16px;
    font-weight: 500;
}
.md-elevation-4{
    box-shadow: none;
}
.md-card-content{
    text-align: center;
}
.user-id span{
    font-weight: 500;
}
.md-card-content{
    padding: 0px;
}

.user-list{
  display: flex;
}
</style>