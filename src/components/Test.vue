<template>

  <datasource ref="remoteDataSource"
    :transport-read-url="'http://localhost:3000/api/orders'"
    :transport-read-data-type="'json'"
    :transport-read-type="'GET'"
    :transport-update-url="'http://localhost:3000/api/orders'"
    :transport-update-data-type="'json'"
    :transport-update-type="'GET'"
    :schema-data="'data'"
    :page-size='20'>
  </datasource>
  <!-- :schema-model-fields="schemaModelFields" -->

  <grid :height="600"
    :data-source-ref="'remoteDataSource'"
    :pageable='true'
    :editable="'inline'">
      <grid-column field="id" title="ID"></grid-column>
      <grid-column field="order_number" title="Order#" :width="120"></grid-column>
      <grid-column field="status" title="Status" :width="120"></grid-column>
      <grid-column :command="['edit']" title="&nbsp;" width="250px"></grid-column>
  </grid>

</template>

<script>
import { DataSource } from '@progress/kendo-datasource-vue-wrapper'
import { Grid, GridColumn } from '@progress/kendo-grid-vue-wrapper'
export default {
  name: 'Test',
  components: {
    'grid': Grid,
		'grid-column': GridColumn,
		'datasource': DataSource,
  },
}
</script>