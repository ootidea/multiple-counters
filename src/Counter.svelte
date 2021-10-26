<script lang="ts">
  import { Button } from 'carbon-components-svelte'
  import TrashCan16 from 'carbon-icons-svelte/lib/TrashCan16'

  export let count: number
  export let title: string
  export let onClickDeleteButton: () => void
</script>

<div>
  {count}
  <input placeholder="title" bind:value={title} />
  <Button
    kind="ghost"
    size="small"
    iconDescription="Delete"
    icon={TrashCan16}
    on:click={onClickDeleteButton}
  />
</div>
