<script lang="ts">
  import Counter from './Counter.svelte'

  type CounterState = { count: number; title: string }

  const counterStates: CounterState[] = [{ count: 0, title: '' }]

  function addNewCounter() {
    counterStates[counterStates.length] = { count: 0, title: '' }
  }
</script>

<main>
  {#each counterStates as counterState}
    <Counter bind:count={counterState.count} bind:title={counterState.title} />
  {/each}
  <button on:click={addNewCounter}>Add new counter</button>
</main>

<style>
</style>
