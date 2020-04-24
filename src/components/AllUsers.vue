<template>
    <div class="wrapper">
            <md-toolbar class="md-transparent" md-elevation="0">
                Users list:
            </md-toolbar>
    <md-card class="user-list" v-for="(user, index) in users" :key="index">
      <md-card-header>
        <div class="md-title"><p>{{ user.name.first }} {{ user.name.last }}</p></div>
      </md-card-header>

      <md-card-content>
        <avatar :image="user.picture.medium" :size="80"/>
        <div class="user-id">
            <p><span>ID: </span> {{ user.id.value }}</p>
        </div>
      </md-card-content>

      <md-card-actions>
        <md-button @click="show">Show info</md-button>
      </md-card-actions>
      <div v-if="visible" :key="index">
        <p>Adress: {{user.location.city}}, {{user.location.street.name}}, {{user.location.street.number}}</p>
        <p>E-mail : {{user.email}}</p>
        <p>Gender : {{user.gender}}</p>
        <p>Dob : {{user.dob.date}}</p>
        <p>Phone number: {{user.phone}}</p>
      </div>
    </md-card>
    </div>
</template>

<script>
import Avatar from 'vue-avatar-component'

export default {
  components: { 
   Avatar
  },
  data () {
    return {
      users: {},
      visible : false
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
    show(){
        this.visible = !this.visible;
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

.user-list{
    max-width: 200px;
    width: 100%;
}

.md-card-content{
    padding: 0px;
}
</style>