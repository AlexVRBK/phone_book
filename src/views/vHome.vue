<template>
  <div class="home">
    <div class="container">
      <AddUsers />
      <UsersTable />
    </div>

  </div>
</template>

<script>
import UsersTable from '@/components/UsersTable';
import AddUsers from '@/components/AddUsers';
export default {
  name: 'vHome',
  components: {
    UsersTable,
    AddUsers
  }
}
</script>

<style scoped>
  .container{
    max-width: 1000px;
    margin: 0 auto;
  }
</style>