<script>
  import Animate from "$lib/Animate.svelte";
  import magic from "$lib/magic-cent.png";
  let magicCent = "000";
  let magicPrincipal;
  let magicInterestRate;
  let n;
  let days;
  $: console.log(days);
  function magicCalculator() {
    // A = Future Amount = MagicCent
    // P = Principal = magicPrincipal
    // r = Interest Rate = magicInterestRate
    // n = Number of periods per year = n
    // t = Number of years = days

    // A = P*(1 +(r/n))^(n*t)

    magicPrincipal = 0.01;
    magicInterestRate = 2;
    n = 1;

    //Math.pow(r, n);
    // magicCent =
    //   magicPrincipal *
    //   Math.pow(1 + magicInterestRate / n, magicInterestRate * days);

    magicCent =
      (magicPrincipal * (-1 + Math.pow(magicInterestRate, days))) / 1 -
      magicInterestRate;

    //magicCent = magicCent / 2;

    // magicCent = magicCent.toFixed(2).replace(/\d(?=(\d{3})+\.)/g, "$&,"); // 12,345.67
  }

  function magicReset() {
    magicCent = "000";
    days = "";
  }
</script>

<Animate>
  <section class="w-full">
    <div class="w-full max-w-screen-xl mx-auto">
      <h1 class="w-full text-5xl text-gray-700">Magic Penny</h1>
      <div class="p-6 md:flex md:flex-cols md:justify-center md:items-center ">
        <img src={magic} alt="" />
      </div>
      <div class="md:flex md:flex-col md:items-center pt-5">
        <div class="input-group ">
          <input
            class="bg-gray-200 md:relative"
            type="number"
            name=""
            id="days"
            placeholder=" "
            bind:value={days}
          />

          <label for="base">Years</label>

          <span class="p-2 md:absolute">days</span>
        </div>
        <div class="md:space-x-8 space-x-4 m-4">
          <button
            class="bg-green-200 md:py-3 md:px-6 py-3 px-4 hover:text-red-300"
            on:click={magicCalculator}>Calculate</button
          >
          <button
            class="bg-yellow-200 md:py-3 md:px-6 py-3 px-4 hover:text-blue-500"
            on:click={magicReset}>Reset</button
          >
        </div>
        <h4 class="text-center">Magic cent</h4>
        <h1><span>$</span><span>{magicCent} </span></h1>
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
