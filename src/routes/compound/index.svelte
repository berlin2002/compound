<script>
  import Animate from "$lib/Animate.svelte";
  import Interest from "./Interest.svelte";
  import Principal from "./Principal.svelte";
  import Rate from "./Rate.svelte";
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
