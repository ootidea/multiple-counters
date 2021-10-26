<script lang="ts">
  import { Button } from 'carbon-components-svelte'
  import Counter from './Counter.svelte'

  type CounterState = { count: number; title: string }

  let counterStates: CounterState[] = [{ count: 0, title: '' }]

  function addNewCounter() {
    counterStates[counterStates.length] = { count: 0, title: '' }
  }

  const onClickDeleteButton = (index) => () => {
    counterStates.splice(index, 1)
    counterStates = counterStates
  }
</script>

<main>
  {#each counterStates as counterState, index}
    <Counter
      bind:count={counterState.count}
      bind:title={counterState.title}
      onClickDeleteButton={onClickDeleteButton(index)}
    />
  {/each}
  <Button kind="primary" size="small" on:click={addNewCounter}>Add new counter</Button>
</main>

<style>
</style>
