<script>
  import Animate from "$lib/Animate.svelte";
  import Interest from "./Future_amount.svelte";
  import Principal from "./Principal.svelte";
  import Rate from "./Interest_rate.svelte";
  import Time from "./Time.svelte";
</script>

<Animate>
  <section class="w-full">
    <div class="w-full max-w-screen-xl mx-auto">
      <div class="w-full">
        <Interest />
        <Principal />
        <Rate />
        <Time />
      </div>
    </div>
  </section>
</Animate>
