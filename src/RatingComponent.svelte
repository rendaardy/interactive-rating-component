<script lang="ts">
  import { createEventDispatcher } from 'svelte';

  import starIcon from './assets/images/icon-star.svg';

  export let maxValue: number;

  const dispatch = createEventDispatcher();
  let values = Array.from({ length: maxValue }, (_, i) => i + 1);
  let selectedValue: number;

  function toggleSelected(value: number): void {
    selectedValue = value;
  }

  function onClick(): void {
    dispatch('selectedValue', selectedValue);
  }
</script>

<section class="rating">
  <div class="icon">
    <img class="icon-star" src={starIcon} alt="Star icon" />
  </div>
  <h4>How did we do?</h4>
  <p>
    Please let us know how we did with your support request. All feedback is appreciated
    to help us improve our offering!
  </p>
  <div class="values">
    {#each values as value}
      <div 
        class:selected={selectedValue === value} 
        on:click={() => toggleSelected(value)} 
        class="value"
      >
        <span>{value}</span>
      </div>
    {/each}
  </div>
  <button class="btn" on:click={onClick} disabled={!selectedValue}>Submit</button>
</section>

<style>
  .rating .icon {
    width: 4.8rem;
    height: 4.8rem;
    border-radius: 50%;
    background-color: hsl(var(--color-medium-grey) / 0.2);
    position: relative;
    margin-bottom: 2.4rem;
  }

  .icon-star {
    display: inline-block;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  .rating {
    background-color: hsl(var(--color-dark-blue));
    padding: 2.4rem;
    border-radius: 23px;
    width: 40rem;
  }

  .rating h4 {
    font-size: 3.2rem;
    font-weight: 700;
    color: hsl(var(--color-white));
    margin-bottom: 1.6rem;
  }

  .rating p {
    font-size: 1.5rem;
    margin-bottom: 2.4rem;
  }

  .rating .values {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    gap: 2.4rem;
    margin-bottom: 2.4rem;
  }

  .rating .value {
    width: 4.8rem;
    height: 4.8rem;
    border-radius: 50%;
    background-color: hsl(var(--color-medium-grey) / 0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: background-color 0.2s ease-in-out;
  }

  .rating .value span {
    display: inline-block;
    font-size: 1.5rem;
    line-height: 0;
  }

  .rating .value.selected {
    background-color: hsl(var(--color-medium-grey));
    color: hsl(var(--color-white));
  }

  .rating .value:hover {
    background-color: hsl(var(--color-primary));
    color: hsl(var(--color-white));
  }

  .rating .btn {
    width: 100%;
    padding: 1.2rem 2.4rem;
    border-radius: 23px;
    font: inherit;
    font-size: 1.5rem;
    background-color: hsl(var(--color-primary));
    color: hsl(var(--color-white));
    cursor: pointer;
    transition: background-color 0.2s ease-in-out;
  }

  .rating .btn:hover {
    background-color: hsl(var(--color-white));
    color: hsl(var(--color-primary));
  }

  @media (max-width: 26.56em) {
    .rating {
      width: 28.6rem;
    }

    .rating .values {
      gap: 0.8rem;
    }
  }
</style>
