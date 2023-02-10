<template>
  <div class="users">
    <div class="users_contact" v-for="user in allUsers" :key="user.id">
      <h2>Name: {{user.name}} </h2>
      <p>Tel: {{user.phone}}</p>
      
      <!-- <b-button href="#" variant="primary">Update</b-button> -->
    <button class="users_delete-btn" @click="deleteUser(user.id)" href="#">Delete</button>
    </div>
</div> 
</template>

<script>
import { mapGetters, mapActions } from 'vuex';
export default {
  name: "UsersTable",
  methods: {
    ...mapActions(['fetchUsers', 'deleteUser', 'updateUser']),
    // onDblClick(user){
    //   const updUser = {
    //     id: user.id,
    //     name: user.name,
    //     phone: user.phone
    //   }
    //   this.updateUser(updUser);
    // }
  },
  computed: mapGetters(['allUsers']),
  created(){
    this.fetchUsers();
  }
};
</script>

<style lang="scss" scoped>
  a{
    color: #fff;
  }
  p{
    font-size: 20px;
    color: rgb(0, 0, 0);
  }
  .users{
    display: flex;
    flex-direction: column;
    border: 2px solid black;
    &_contact{
      border: 1px solid black;
    }
    &_delete-btn{
      padding: 10px;
      background: rgb(255, 71, 71);
      border-radius: 7px;
      margin-bottom: 10px;
    }
  }
  .card{
    width: 300px;
    margin-bottom: 10px;
  }
 
</style>