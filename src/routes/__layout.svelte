<script>
  import "../app.css";
  import { page } from "$app/stores";
</script>

<section class="w-full">
  <div class="w-full max-w-screen-xl mx-auto md:p-4">
    <div class="font-bold md:text-5xl lg:text-7xl text-3xl mt-8">
      BEE CALCULATOR
    </div>
    <div class=" md:flex hidden">
      <div class="w-full border-black border-b-2 my-12" />
      <nav>
        <ul class="flex justify-between">
          <li class="py-8 px-4" class:active={$page.path === "/"}>
            <a sveltekit:prefetch href="/">Home</a>
          </li>
          <li class="py-8 px-4" class:active={$page.path === "/rectangle"}>
            <a sveltekit:prefetch href="/rectangle">Rectangle Area</a>
          </li>
          <li class="py-8 px-4" class:active={$page.path === "/triangle"}>
            <a sveltekit:prefetch href="/triangle">Triangle Area</a>
          </li>
          <li
            class="py-8 px-4"
            class:active={$page.path === "/simple_interest"}
          >
            <a sveltekit:prefetch href="/simple_interest">Simple Interest</a>
          </li>
          <li class="py-8 px-4" class:active={$page.path === "/magic_penny"}>
            <a sveltekit:prefetch href="/magic_penny">Magic Penny</a>
          </li>
        </ul>
      </nav>
    </div>

    <div class="md:hidden">
      <div class="">
        <nav class="absolute right-0 logo w-14">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6 relative "
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
          </svg>
        </nav>
      </div>
    </div>
  </div>
</section>

<main>
  <slot />
</main>
