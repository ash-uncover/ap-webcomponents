<script>
  import ApGridBuilder from '../lib/ApGridBuilder.svelte'
  import ApGridBuilderWidget from '../lib/ApGridBuilderWidget.svelte'
</script>

<ApGridBuilder columns={16} rows={10}>

  <ApGridBuilderWidget
    backgroundColor={'yellow'}
    height={3}
    width={3}
    column={2}
    row={4}
  />

  <ApGridBuilderWidget
    backgroundColor={'red'}
  />

  <ApGridBuilderWidget
    backgroundColor={'green'}
  />

  <ApGridBuilderWidget
    backgroundColor={'blue'}
    width={1}
    />

  <ApGridBuilderWidget
    backgroundColor={'magenta'}
  />

  <ApGridBuilderWidget
    backgroundColor={'gold'}
  />

  <ApGridBuilderWidget
    backgroundColor={'orange'}
    width={1}
    />

  <ApGridBuilderWidget
    backgroundColor={'lightgreen'}
  />

  <ApGridBuilderWidget
    backgroundColor={'lightblue'}
  />

</ApGridBuilder>
