<template>
    <ejs-grid :dataSource="jobs">
      <e-columns>
        <e-column field="title" headerText="Job Title" textAlign="Right" :isPrimaryKey="true" width="100"></e-column>
        <e-column field="id" headerText="ID"  width="80"></e-column>
        <e-column field="details" headerText="Details" width="90"></e-column>
      </e-columns>
    </ejs-grid>
</template>

<script>
import { GridComponent, ColumnsDirective, ColumnDirective } from '@syncfusion/ej2-vue-grids';
  // Component registration
  export default {
    name: "Charts",
    components: {
      'ejs-grid' : GridComponent,
      'e-columns' : ColumnsDirective,
      'e-column' : ColumnDirective
    },
      // Bound properties declarations
      data() {
        return {
          jobs: [],
        }
      },
      mounted() {
        fetch('http://localhost:3000/jobs')
        .then(res => res.json())
        .then(data => this.jobs = data)
        .catch(err => console.log(err.message))
  }
}
  
</script>

<style >

 

</style>
