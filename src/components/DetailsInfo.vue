<template>
     <div class="wrapper">
            <p>Adress: {{user_data.location.city}}, {{user_data.location.street.name}}, {{user_data.location.street.number}}</p>
            <p>E-mail : {{user_data.email}}</p>
            <p>Gender : {{user_data.gender}}</p>
            <p>Dob : {{user_data.dob.date}}</p>
            <p>Phone number: {{user_data.phone}}</p>
      </div>
</template>
<script>
export default {
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