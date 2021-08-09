<script>
  import Animate from "$lib/Animate.svelte";
  import { page } from "$app/stores";
</script>

<Animate>
  <div class="md:flex">
    <section class="w-max-w-1/4 p-8">
      <div class="w-full max-w-screen-xl mx-auto">
        <div class="bg-pink-200 md:p-12 md:h-full m-8 text-2xl">
          <nav>
            <ul>
              <li class="" class:active={$page.path === "/compound/Interest"}>
                <a
                  class="text-pink-900 hover:text-blue-600"
                  sveltekit:prefetch
                  href="/compound/Future_Amount">Future Amount</a
                >
              </li>

              <li class="" class:active={$page.path === "/compound/Principal"}>
                <a
                  class="text-pink-900 hover:text-blue-600"
                  sveltekit:prefetch
                  href="/compound/Principal">Compound Principal</a
                >
              </li>

              <li class="" class:active={$page.path === "/compound/Rate"}>
                <a
                  class="text-pink-900 hover:text-blue-600"
                  sveltekit:prefetch
                  href="/compound/Interest_rate">Interest Rate</a
                >
              </li>

              <li class="" class:active={$page.path === "/compound/Time"}>
                <a
                  class="text-pink-900 hover:text-blue-600"
                  sveltekit:prefetch
                  href="/compound/Time">Compound Time</a
                >
              </li>
            </ul>
          </nav>
        </div>
      </div>
    </section>
    <div class="w-max-3/4 w-full">
      <slot />
    </div>
  </div>
</Animate>
