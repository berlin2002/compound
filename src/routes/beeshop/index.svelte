<script>
  import Animate from "$lib/Animate.svelte";
  import image1 from "$lib/download.jpg";
  import image2 from "$lib/81ZM1VsoaaL._AC_SY450_.jpg";
  import image3 from "$lib/main-qimg-03e610588058f770c4df96aed0b3f3b6.png";
  import image4 from "$lib/EEIJJdAVUAYXFgq.jpg";
</script>

<Animate>
  <section class="w-full">
    <div class="w-full max-w-screen-xl bg-pink-300 mx-auto hover:bg-blue-400">
      <h1 class=" md:text-8xl   font-bold">
        <span
          class="text-red-800 hover:text-white md:hover:text-7xl hover:text-3xl"
          >Trust</span
        >
        <span
          class="text-black hover:text-blue-900 md:hover:text-7xl hover:text-3xl"
          >Berlin</span
        >
        <span
          class="text-purple-800 hover:text-red-800 md:hover:text-7xl hover:text-3xl"
          >Phone</span
        >
      </h1>

      <div class="md:flex md:flex-row w-full max-w-screen-xl">
        <img class="w-4/6 md:w-2/5 md:h-96 md:p-4 p-4 " src={image1} alt="" />
        <img class="w-4/6 md:w-3/4 md:h-96 md:p-4 p-4 " src={image2} alt="" />
        <img class="w-4/6 md:w-3/4 md:h-96 md:p-4 p-4 " src={image3} alt="" />
        <img class="w-4/6 md:w-3/4 md:h-96 md:p-4 p-4 " src={image4} alt="" />
      </div>
    </div>
  </section>
</Animate>
