<script>
  import Animate from "$lib/Animate.svelte";
  let principal;
  let interestRate;
  let years;
  let simpleInterest = "000";
  let growth = "000";
  function simpleCalculator() {
    simpleInterest = principal * (1 + (interestRate / 100) * years);
    growth = simpleInterest - principal;
  }

  function reset() {
    principal = "";
    interestRate = "";
    years = "";
    simpleInterest = "000";
    growth = "000";
  }
</script>

<Animate>
  <section class="w-full">
    <div class="w-full max-w-screen-xl mx-auto">
      <h1 class="w-full text-5xl text-gray-700">Simple Interest</h1>
      <div class="md:flex md:flex-col md:items-center ">
        <div class="input-group ">
          <span class="p-2 md:absolute">$</span>
          <input
            class="bg-gray-200 md:relative"
            type="number"
            name=""
            id="principal"
            placeholder=" "
            bind:value={principal}
          />

          <label for="width">Principal</label>

          <span class="p-2 md:absolute">.00</span>
        </div>

        <div class="input-group ">
          <input
            class="bg-gray-200 md:relative"
            type="number"
            name=""
            id="interestRate"
            placeholder=" "
            bind:value={interestRate}
          />

          <label for="width">Inrerest Rate</label>

          <span class="p-2 md:absolute">%</span>
        </div>

        <div class="input-group ">
          <input
            class="bg-gray-200 md:relative"
            type="number"
            name=""
            id="years"
            placeholder=" "
            bind:value={years}
          />

          <label for="width">Years</label>

          <span class="p-2 md:absolute">years</span>
        </div>

        <div class="md:space-x-8 space-x-4 m-4">
          <button
            class="bg-green-200 md:py-3 md:px-6 py-3 px-4 hover:text-red-300"
            on:click={simpleCalculator}>Calculate</button
          >
          <button
            class="bg-yellow-200 md:py-3 md:px-6 py-3 px-4 hover:text-blue-500"
            on:click={reset}>Reset</button
          >
        </div>
        <div class="">
          <h4 class="text-center">The balance after <span>5</span> years is</h4>
          <h1>$<span>{simpleInterest}</span></h1>
          <h1>
            <span>($<span>{growth}</span> <span>growth</span>)</span>
          </h1>
        </div>
      </div>
    </div>
  </section>

  <style>
    :root {
      --body: #ffffff;
      --text: #363636;
      --text-light: #898989;
      --primary: #1bbeff;
      /* --border: #bbbbbb; */
      --padding: 16px 24px;
      --line-height: 24px;
    }

    body {
      background-color: var(--body);
    }

    .input-group {
      width: 360px;
      position: relative;
      /* border: 3px solid var(--border); */
      /* border-radius: 8px; */
      margin: 12px;
    }
    .input-group input {
      padding: var(--padding);
      /* border: none; */
      /* background-color: transparent; */
      width: 100%;
      color: var(--text);
      font-size: 16px;
      line-height: var(--line-height);
    }

    .input-group:hover,
    .input-group:focus-within {
      /* border-color: var(--primary); */
    }

    .input-group input:focus,
    .input-group:hover input {
      color: var(--primaty);
    }

    .input-group label {
      position: absolute;
      background-color: transparent;
      padding: var(--padding);
      line-height: var(--line-height);
      top: 0;
      left: 0;
      bottom: 0;
      color: var(--text-light);
      cursor: text;
    }

    .input-group:hover label {
      color: var(--primary);
    }

    .input-group:focus-within label,
    .input-group input:not(:placeholder-shown) ~ label {
      padding: 0px 8px;
      background-color: var(--body);
      top: -12px;
      left: 16;
      bottom: auto;
      color: var(--text);
    }
  </style>
</Animate>
