<template>

  <div class="users">
    <input type="text" placeholder="Type a name" v-model="authorNameSearchString" />
    <br>
    <p  @click="sortBy()" class="material-icons">+</p>
    <br>
    <div class="users_contact" v-for="user in allUsers" :key="user.id">
      <h2> {{user.name}} </h2>
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
  
  data() {
        return {
            users: "",
            sortedUser: this.allUsers,
        }
    },

  methods: {
    ...mapActions(['fetchUsers', 'deleteUser', 'updateUser']),
       sortBy() {
      this.sortedUser = this.sortedUser.sort((a, b) => b.name > a.name)
    },
    
  },
  computed: {...mapGetters(['allUsers'])},


  


  created(){
    this.fetchUsers();
  },
  mounted(){
    console.log(this.allUsers)
  }
};
</script>

<style lang="scss" scoped>
  a{
    color: #fff;
  }
   h2 {
    margin: 0;
    padding: 0;
    font-size: 1.5rem;
   }
  p{
    font-size: 20px;
    color: rgb(0, 0, 0);
  }
  .users{
    display: flex;
    flex-direction: column;
    
    border-radius: 8px;
    &_contact{
      border: 1px solid black;
        background: rgb(243, 229, 203);
        border-radius: 8px;
        margin-bottom: 5px;
    }
    &_delete-btn{
      padding: 5px;
      color: black;
      background: #f8e1ed;
      border-radius: 8px;
      margin-bottom: 10px;
      cursor: pointer;
      
    }
  }
  .card{
    width: 300px;
    margin-bottom: 10px;
  }
  .material-icons{
    font-size: 20px;
    cursor: pointer;
  }
 
</style>