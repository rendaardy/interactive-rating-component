<script lang="ts">
  import RatingComponent from "./RatingComponent.svelte";
  import ThankYouComponent from "./ThankYouComponent.svelte";

  let maxValue = 5;
  let selectedValue: number;

  function onSelectedValue(event: CustomEvent): void {
    selectedValue = event.detail as number;
  }
</script>

<main>
  <div class="container">
    {#if !selectedValue}
      <RatingComponent {maxValue} on:selectedValue={onSelectedValue} />
    {:else}
      <ThankYouComponent value={selectedValue} {maxValue} />
    {/if}
  </div>
</main>

<style>
  .container {
    height: 100vh;
    display: grid;
    grid-template-columns: 1fr;
    place-items: center;
  }
</style>
