<script>
  export let width = 1
  export let height = 1
  export let row
  export let column

  export let backgroundColor = '#F5F5F5'
</script>

<div
  class='ap-grid-builder-widget'
  style={[
    `background: ${backgroundColor}`,
    row ? `grid-row:${row}${height ? ` / span ${height}` : ''}` : '',
    column ? `grid-column:${column}${width ? ` / span ${width}` : ''}` : ''
  ].join(';')}
>
  <slot />
</div>

<style>
  .ap-grid-builder-widget {
    overflow: hidden;
    width: 100%;
    height: 100%;

    pointer-events: auto;
    cursor: pointer;

    box-sizing: border-box;

  }
</style>