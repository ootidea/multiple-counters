<script lang="ts">
  export let count: number
  export let title: string
</script>

<div>
  {count}
  <input placeholder="title" bind:value={title} />
</div>
