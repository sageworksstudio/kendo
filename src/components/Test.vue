<template>

  <datasource ref="remoteDataSource"
    :transport-read-url="'https://my-json-server.typicode.com/sageworksstudio/json-server/test'"
    :transport-read-data-type="'json'"
    :transport-read-type="'GET'"
    :transport-update-url="'https://my-json-server.typicode.com/sageworksstudio/json-server/test'"
    :transport-update-data-type="'json'"
    :transport-update-type="'GET'"
    :schema-model-id="'ProductID'"
    :page-size='20'>
  </datasource>
  <!-- :schema-model-fields="schemaModelFields" -->

  <grid :height="600"
    :data-source-ref="'remoteDataSource'"
    :pageable='true'
    :editable="'inline'">
      <grid-column field="id"></grid-column>
      <grid-column field="title" title="Title" :width="120"></grid-column>
      <grid-column field="active" title="Active" :width="120"></grid-column>
      <grid-column :command="['edit']" title="&nbsp;" width="250px"></grid-column>
  </grid>

</template>

<script>
import { DataSource } from '@progress/kendo-datasource-vue-wrapper'
import { Grid, GridColumn } from '@progress/kendo-grid-vue-wrapper'
export default {
  name: 'App',
  components: {
    'grid': Grid,
		'grid-column': GridColumn,
		'datasource': DataSource,
  },
}
</script>