<template>
     <div class="wrapper">
            <avatar :image="user.picture.medium" :size="100"/>
            <p>Adress: {{user.location.city}}, {{user.location.street.name}}, {{user.location.street.number}}</p>
            <p>E-mail : {{user.email}}</p>
            <p>Gender : {{user.gender}}</p>
            <p>Dob : {{user.dob.date}}</p>
            <p>Phone number: {{user.phone}}</p>
      </div>
</template>
<script>
import Avatar from 'vue-avatar-component'
export default {
  components:{
    Avatar
  },
  props:{
    user: {
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
</style>