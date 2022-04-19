<script lang="ts">
  import illustrationThankYou from './assets/images/illustration-thank-you.svg';

  export let value: number;
  export let maxValue: number;
</script>

<section class="thank-you">
  <div class="img-box">
    <img class="illustration" src={illustrationThankYou} alt="Illustration thank you" />
  </div>
  <div class="result">
    <span>You selected {value} out of {maxValue}</span>
  </div>
  <h4>Thank You!</h4>
  <p>
    We appreciate you taking the time to give a rating. If you ever need more support,
    don't hesitate to get in touch!
  </p>
</section>

<style>
  .thank-you {
    width: 40rem;
    padding: 4.8rem 2.4rem;
    background-color: hsl(var(--color-dark-blue));
    border-radius: 23px;
    text-align: center;
  }

  .img-box {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 2.4rem;
  }

  .result {
    margin-bottom: 2.4rem;
  }

  .result span {
    display: inline-block;
    padding: 0.8rem 1.6rem;
    border-radius: 23px;
    background-color: hsl(var(--color-medium-grey) / 0.2);
    color: hsl(var(--color-primary));
    font-size: 1.2rem;
  }

  .thank-you h4 {
    font-size: 3.2rem;
    font-weight: 700;
    color: hsl(var(--color-white));
    margin-bottom: 1.6rem;
  }

  .thank-you p {
    font-size: 1.5rem;
  }
</style>
