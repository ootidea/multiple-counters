<script lang="ts">
  import { Button } from 'carbon-components-svelte'
  import PlusIcon from 'carbon-icons-svelte/lib/Add32'
  import ResetIcon from 'carbon-icons-svelte/lib/Reset32'
  import MinusIcon from 'carbon-icons-svelte/lib/Subtract32'
  import TrashCan16 from 'carbon-icons-svelte/lib/TrashCan16'

  export let count: number
  export let title: string
  export let onClickDeleteButton: () => void
</script>

<div>
  {count}
  <Button kind="tertiary" size="small" icon={PlusIcon} iconDescription="Increment" />
  <Button kind="tertiary" size="small" icon={MinusIcon} iconDescription="Decrement" />
  <Button kind="tertiary" size="small" icon={ResetIcon} iconDescription="Reset" />
  <input placeholder="title" bind:value={title} />
  <Button
    kind="ghost"
    size="small"
    iconDescription="Delete"
    icon={TrashCan16}
    on:click={onClickDeleteButton}
  />
</div>
