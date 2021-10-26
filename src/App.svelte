<script lang="ts">
  import { Button } from 'carbon-components-svelte'
  import Counter from './Counter.svelte'

  type CounterState = { count: number; title: string }

  let counterStates: CounterState[] = [{ count: 0, title: '' }]

  $: sum = counterStates.reduce((value, counterState) => value + counterState.count, 0)

  function addNewCounter() {
    counterStates[counterStates.length] = { count: 0, title: '' }
  }

  const onClickDeleteButton = (index) => () => {
    counterStates.splice(index, 1)
    counterStates = counterStates
  }
</script>

<main class="container mx-auto mt-12">
  <div class="w-max mx-auto">
    <div class="flex flex-col gap-2">
      {#each counterStates as counterState, index}
        <Counter
          bind:count={counterState.count}
          bind:title={counterState.title}
          onClickDeleteButton={onClickDeleteButton(index)}
        />
      {/each}
    </div>
    <div>{sum}</div>
    <Button class="block w-max mx-auto" kind="primary" size="small" on:click={addNewCounter}
      >Add new counter
    </Button>
  </div>
</main>

<style>
</style>
