<script lang="ts">
  export let count: number
  export let title: string
  export let onClickDeleteButton: () => void
</script>

<div>
  {count}
  <input placeholder="title" bind:value={title} />
  <button on:click={onClickDeleteButton}>Delete</button>
</div>
