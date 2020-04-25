<template>
     <div class="wrapper">
            <avatar :image="user_data.picture.medium" :size="100"/>
            <p>Adress: {{user_data.location.city}}, {{user_data.location.street.name}}, {{user_data.location.street.number}}</p>
            <p>E-mail : {{user_data.email}}</p>
            <p>Gender : {{user_data.gender}}</p>
            <p>Dob : {{user_data.dob.date}}</p>
            <p>Phone number: {{user_data.phone}}</p>
      </div>
</template>
<script>
import Avatar from 'vue-avatar-component'
export default {
  components:{
    Avatar
  },
  props:{
    user_data: {
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