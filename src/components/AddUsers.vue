<template>

  <div class="form">
    
     <form @submit="onSubmit">
      <div>
        <label for="name">Name:</label>
        <input id="name" type="text" v-model="form.name" required placeholder="Enter name" />
      </div>
      <div>
        <label for="Your Telephone number">Phone:</label>
        <input id="phone" type="number"  v-model="form.phone" required   placeholder="Enter telephone number..."/>
      </div>
      <button type="submit" variant="primary">Submit</button>
      
    </form>
    
   
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "AddUser",
  methods: {
    ...mapActions(["addUser"]),
    onSubmit(e) {
      e.preventDefault();
      const newUser = {
        name: this.form.name,
        phone: this.form.phone,
      };
      this.addUser(newUser);
      this.form.name = "";
      this.form.phone = "";
    },
  },
  data() {
    return {
      form: {
        name: "",
        phone: "",
      },
    };
  },
};
</script>

<style lang="scss" scoped>

.form {
  max-width: 600px;
  margin: 0 auto;
  border: 2px solid black;
  margin-bottom: 10px;
  border-radius: 8px;
  background: rgb(243, 229, 203);
}
form {
  padding: 20px;

  
}
button{
     padding: 5px;
      color: black;
      background: #f8e1ed;
      border-radius: 8px;
      margin-bottom: 10px;
      cursor: pointer;
}
#name{
   max-width: 500px;
  border: none;
  margin-bottom: 0.5rem;
  border-radius: 6rem;
  &::placeholder {
    font-family: "Open Sans", serif;
    font-size: .875rem;
    padding: .5rem;
  }
}
#phone{
   max-width: 500px;
  border: none;
  margin-bottom: 0.5rem;
  border-radius: 6rem;
  &::placeholder {
    font-family: "Open Sans", serif;
    font-size: .875rem;
    padding: .5rem;
  }
}

</style>