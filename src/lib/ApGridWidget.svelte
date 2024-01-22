<svelte:options customElement='ap-grid-widget' />

<script>
  export let width = 1
  export let height = 1
  export let top = 0
  export let left = 0

  export let backgroundColor = '#F5F5F5'
</script>

<div
  class='ap-grid-widget'
  style={[
    `background: ${backgroundColor}`
  ].join(';')}
>
  <slot />
</div>

<style>
  .ap-grid-widget {
    padding: 0.25rem;
    border: 1px solid grey;

    aspect-ratio: 1;
    overflow: hidden;
  }
</style>