<template>
  <div class="about">
    <v-container fluid>
      <AddingTank />  
      <TableComponent msg='Dodavanje u tank'/>
    </v-container>
  </div>
</template>

<script>
import TableComponent from "@/components/TableComponent.vue";
import AddingTank from "@/components/AddingTank.vue";
export default {
  name: "About",
  components: {
    TableComponent,
    AddingTank
  }
};
</script>
