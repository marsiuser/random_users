<template>
     <div class="wrapper">
            <md-card class="list-cart">
          <md-card-header>
                <div class="md-title"><p>{{ user.name.first }} {{ user.name.last }}</p></div>
          </md-card-header>
          <md-card-content>
            <avatar :image="user.picture.medium" :size="80"/>
            <div class="user-id">
                <p><span>ID: </span> {{ user.id.value }}</p>
            </div>
            <md-card-actions>
                  <md-button @click="viewDetailsClicked">Show info</md-button>
            </md-card-actions>
          </md-card-content>
      </md-card>
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
    },
    index:{
      type: Number
    }
  },
  data(){
    return{}
  },
  methods:{
    viewDetailsClicked(){
      this.$emit("viewDetails",  this.user.id.value);
    }
  }
}
</script>

<style lang="scss">
.list-cart .md-card-header,
.md-card-content:last-of-type{
    padding: 0px;
}

</style>