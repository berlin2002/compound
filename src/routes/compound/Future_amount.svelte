<script>
  import Animate from "$lib/Animate.svelte";
  let futureAmount;
  let compoundFrequency = 1.0;
  let principalAmount;
  let rateOfInterest;
  let timeInYears;
  let periodics;
  let periodicTotal;

  // A = futureAmount
  // P = principalAmount
  // n = compoundFrequency
  // t = timeInYears
  // r = rateOfInterest

  // document.querySelector("#answer").innerHTML = futureAmount;
  // document.querySelector("#annual_cut").innerHTML = annual_cut;
  // document.querySelector("#monthly_cut").innerHTML = monthly_cut;

  function futAmount() {

      console.log(
        "Principal:",
        principalAmount,
        "Interest:",
        rateOfInterest,
        "Periodics:",
        periodics,
        "Frequency:",
        compoundFrequency,
        "Time:",
        timeInYears
      );
    
    rateOfInterest = rateOfInterest/100;
    
    principalAmount *
      Math.pow(
        1 + rateOfInterest / compoundFrequency,
        compoundFrequency * timeInYears
      );

    periodicTotal =
      periodics *
      ((Math.pow(
        1 + rateOfInterest / compoundFrequency,
        compoundFrequency * timeInYears
      ) -
        1) /
        (rateOfInterest / compoundFrequency));

    futureAmount = futureAmount + periodicTotal;

    // let annual_cut = futureAmount * rateOfInterest;
    // let monthly_cut = annual_cut / 12;

    futureAmount = futureAmount.toFixed(2).replace(/\d(?=(\d{3})+\.)/g, "$&,"); // 12,345.67
    // annual_cut = annual_cut.toFixed(2).replace(/\d(?=(\d{3})+\.)/g, "$&,"); // 12,345.67
    // monthly_cut = monthly_cut.toFixed(2).replace(/\d(?=(\d{3})+\.)/g, "$&,"); // 12,345.67
  }

  function compoundReset() {
    futureAmount = "0.00";
    annual_cut = "0.00";
    monthly_cut = "0.00";
    principalAmount = "";
  }
</script>

<Animate>
  <section class="w-full">
    <div class="w-5/6 max-w-screen-xl mb-8 mt-4 mx-auto  bg-yellow-200 ">
      <h1 class="text-pink-800 text-3xl md:text-5xl">Future Amount</h1>

      <div class=" md:flex md:flex-col md:items-center pt-5">
        <div class="input-group ">
          <input
            class="bg-gray-200 md:relative"
            type="number"
            name=""
            id="principal"
            placeholder=" "
            bind:value={principalAmount}
          />

          <label for="principal">Principal</label>

          <span class="p-2 md:absolute">$.00</span>
        </div>
      </div>

      <div class=" md:flex md:flex-col md:items-center pt-5">
        <div class="input-group ">
          <input
            class="bg-gray-200 md:relative"
            type="number"
            name=""
            id="contributions"
            placeholder=" "
            bind:value={periodics}
          />

          <label for="contributions">Additional Contributions Annually</label>

          <span class="p-2 md:absolute">$.00</span>
        </div>
      </div>

      <div class=" md:flex md:flex-col md:items-center pt-5">
        <div class="input-group ">
          <input
            class="bg-gray-200 md:relative"
            type="number"
            name=""
            id="rate"
            placeholder=" "
            bind:value={rateOfInterest}
          />

          <label for="rate">Interest Rate</label>

          <span class="p-2 md:absolute">%</span>
        </div>
      </div>

      <div class=" md:flex md:flex-col md:items-center pt-5">
        <div class="input-group ">
          <input
            class="bg-gray-200 md:relative"
            type="number"
            name=""
            id="years"
            placeholder=""
            bind:value={timeInYears}
          />

          <label for="years">Years</label>

          <span class="p-2 md:absolute">Years</span>
        </div>
      </div>

      <div class=" md:flex md:flex-col md:items-center pt-5">
        <div class="md:space-x-8 space-x-8 m-4">
          <button
            class="btn md:py-2 md:px-8 py-2 px-2 hover:text-red-300"
            on:click={futAmount}>Calculate</button
          >
          <button class="btn  md:py-2 md:px-8 py-2 px-2 hover:text-blue-500"
            >Reset</button
          >
        </div>
      </div>

      <div class=" md:flex md:flex-col md:items-center pt-5">
        <div>
          <h4>Compounded Balance</h4>
          <h1><span>$</span>{futureAmount}<span /></h1>
          <h5>
            Annual Earnings <span>$</span><span />
          </h5>
          <h5>Monthly Earnings <span>$</span><span /></h5>
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

    .btn {
      background-color: #c65b00;
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
