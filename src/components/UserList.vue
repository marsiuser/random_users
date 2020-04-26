<template>
    <div class="wrapper">
    <md-toolbar class="md-transparent" md-elevation="0">
        Users list:
    </md-toolbar>
    <div class="user-list">
            <UserItem v-for="(user, i) in users" :key="user.id" :user="user" :index="(i+1)" @viewDetails="viewDetails" />
        </div>
    </div>
</template>

<script>
import Avatar from 'vue-avatar-component'
import _ from 'lodash';

export default {
  components: { 
   Avatar,
    UserItem: () => import('./UserItem')
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
      viewDetails(id){
      let userToView = _.find(this.users);
      this.$emit("viewDetails", userToView);
      console.log(userToView);
    }
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

</style>