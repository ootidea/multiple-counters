<script lang="ts">
  import { Button } from 'carbon-components-svelte'
  import PlusIcon from 'carbon-icons-svelte/lib/Add32'
  import ResetIcon from 'carbon-icons-svelte/lib/Reset32'
  import MinusIcon from 'carbon-icons-svelte/lib/Subtract32'
  import TrashCan16 from 'carbon-icons-svelte/lib/TrashCan16'

  export let count: number
  export let title: string
  export let onClickDeleteButton: () => void

  function increment() {
    count++
  }

  function decrement() {
    if (count > 0) {
      count--
    }
  }

  function reset() {
    count = 0
  }
</script>

<div class="flex items-center gap-1">
  <input placeholder="title" bind:value={title} />
  <span class="text-xl px-4">{count}</span>
  <Button
    kind="tertiary"
    size="small"
    icon={PlusIcon}
    iconDescription="Increment"
    on:click={increment}
  />
  <Button
    kind="tertiary"
    size="small"
    icon={MinusIcon}
    iconDescription="Decrement"
    on:click={decrement}
  />
  <Button kind="tertiary" size="small" icon={ResetIcon} iconDescription="Reset" on:click={reset} />
  <Button
    kind="ghost"
    size="small"
    iconDescription="Delete"
    icon={TrashCan16}
    on:click={onClickDeleteButton}
  />
</div>
