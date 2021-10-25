<script lang="ts">
  import Counter from './Counter.svelte'

  type CounterState = { count: number; title: string }

  const counterStates: CounterState[] = [{ count: 0, title: '' }]
</script>

<main>
  {#each counterStates as counterState}
    <Counter bind:count={counterState.count} bind:title={counterState.title} />
  {/each}
</main>

<style>
</style>
