<script>
  export let width = 1;
  export let height = 1;
  export let row;
  export let column;

  export let backgroundColor = "#F5F5F5";

  function handleDragStart(event) {
    console.log('drag')
    event.dataTransfer.effectAllowed = "move"
    event.dataTransfer.dropEffect = "move"
  }
</script>

<div
  class="ap-grid-builder-widget"
  style={[
    `background: ${backgroundColor}`,
    row ? `grid-row:${row}${height ? ` / span ${height}` : ""}` : "",
    column ? `grid-column:${column}${width ? ` / span ${width}` : ""}` : "",
  ].join(";")}
  draggable="true"
  role="gridcell"
  tabindex="0"
  on:dragstart={handleDragStart}
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
