<svelte:options customElement='ap-grid-builder' />

<script>
  export let columns = 1;
  export let rows = 1;

  let blocks = [];
  $: {
    blocks = [];
    for (let x = 0; x < rows; x++) {
      for (let y = 0; y < columns; y++) {
        blocks.push({
          class: (x === rows - 1 || y === columns - 1) ? 'hide-dot' : '',
          index: x + y * x,
          x,
          y
        });
      }
    }
  }
</script>

<div class='ap-grid-builder'>

  <div
    class='ap-grid-builder-background'
    style={[
      `grid-template-columns: repeat(${columns}, 1fr)`,
      `grid-template-rows: repeat(${rows}, 1fr)`,
    ].join(';')}
  >
    {#each blocks as block}
      <div class={`ap-grid-builder-block ${block.class}`} />
    {/each}
  </div>

  <div
    class='ap-grid-builder-content'
    style={[
      `grid-template-columns: repeat(${columns}, 1fr)`,
      `grid-template-rows: repeat(${rows}, 1fr)`,
    ].join(';')}
  >
    <slot />
  </div>
</div>

<style>
  .ap-grid-builder {
    position: relative;
    border: 2px solid black;
    box-sizing: border-box;
    width: 100%;
    height: 100%;
  }

  .ap-grid-builder-grid {
    display: grid;
  }

  .ap-grid-builder-background {
    width: 100%;
    height: 100%;

    display: grid;
    grid-gap: 1px;
  }

  .ap-grid-builder-background .ap-grid-builder-block {
    position: relative;
    box-sizing: border-box;
    border: 1px solid transparent;
    aspect-ratio: 1;
  }
  .ap-grid-builder-background .ap-grid-builder-block:hover {
    background: #F8F8F8;
    border: 1px solid #F3F3F3;
  }
  .ap-grid-builder-background .ap-grid-builder-block:not(.hide-dot):after {
    content: '';
    position: absolute;
    bottom: -2px;
    right: -2px;
    width: 1px;
    height: 1px;
    background: black;
  }

  .ap-grid-builder-content {
    position: absolute;
    top: 0;
    left: 0;

    width: 100%;
    height: 100%;

    display: grid;
    grid-gap: 1px;

    pointer-events: none;
  }
</style>
