<script>
  import Animate from "$lib/Animate.svelte";
  let width;
  let length;
  let rectangleArea = "000";

  function rectCalculator() {
    rectangleArea = length * width;
    console.log(rectangleArea);
  }

  function reset() {
    length = "";
    width = "";
    rectangleArea = "000";
  }
</script>

<Animate>
  <section class="w-full">
    <div class="w-full max-w-screen-xl mx-auto ">
      <h1 class="w-full md:text-5xl text-3xl pt-4 text-gray-700">
        Rectangle Area
      </h1>
      <div class=" md:flex md:flex-col md:items-center pt-5">
        <div class="input-group ">
          <input
            class="bg-gray-200 md:relative"
            type="number"
            name=""
            id="width"
            placeholder=" "
            bind:value={width}
          />

          <label for="width">Width</label>

          <span class="p-2 md:absolute">cm</span>
        </div>
        <div class="input-group">
          <input
            class="bg-gray-200 md:relative"
            type="number"
            name=""
            id="length"
            placeholder=" "
            bind:value={length}
          />
          <label for="length">Length</label>

          <span class="p-2 md:absolute">cm</span>
        </div>

        <div class="md:space-x-8 space-x-4 m-4">
          <button
            class="bg-green-200 md:py-3 md:px-6 py-3 px-4 hover:text-red-300"
            on:click={rectCalculator}>Calculate</button
          >
          <button
            class="bg-yellow-200 md:py-3 md:px-6 py-3 px-4 hover:text-blue-500"
            on:click={reset}>Reset</button
          >
        </div>

        <div class="">
          <h4 class="text-center">Area of rectangle is</h4>
          <h1>
            <span class="">{rectangleArea}</span><span>cm<sup>2</sup> </span>
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
