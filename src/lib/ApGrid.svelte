<svelte:options customElement='ap-grid' />

<script>
  export let columns = 1
  export let rows = 1
</script>

<div
  class='ap-grid'
>
  <div
    class='ap-grid-grid ap-grid-background'
    style={[
      `grid-template-columns: repeat(${columns}, 1fr)`,
      `grid-template-rows: repeat(${rows}, 1fr)`
    ].join(';')}
  >

  </div>

  <div
    class='ap-grid-grid ap-grid-content'
    style={[
      `grid-template-columns: repeat(${columns}, 1fr)`,
      `grid-template-rows: repeat(${rows}, 1fr)`
    ].join(';')}
  >
    <slot />
  </div>

</div>

<style>
  .ap-grid {
    position: relative;
    border: 2px solid black;
    padding: 0.5rem;
  }

  .ap-grid-grid {
    display: grid;
    grid-gap: 0.5rem;
  }

  .ap-grid-background {
    position: absolute;
  }

  .ap-grid-content {
  }
</style>