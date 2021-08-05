<script>
  import Animate from "$lib/Animate.svelte";
  import image from "$lib/85ff5a9e-c6f6-489b-85f6-46fc6d9a2d6b_900_900.png";
  import image2 from "$lib/area-triangle.png";
  import image3 from "$lib/C-2V3.png";
  import image4 from "$lib/61XjLJx+LLL._AC_SX355_.jpg";
</script>

<Animate>
  <section class="w-full">
    <div class="w-full max-w-screen-xl mx-auto">
      <h1 class="w-full md:text-7xl text-5xl pt-4 text-gray-700">CALCULATOR</h1>

      <!-- <div><h1 class="text-blue-600 pt-32 text-5xl">Rectangle</h1></div> -->
      <div class="p-6 md:flex md:flex-cols md:justify-center md:items-center ">
        <p class="p-4">
          <span class="text-2xl font-bold text-blue-600"> Definition </span>
          By definition, the area of a rectangle is the region covered by the rectangle
          in a two-dimensional plane. A rectangle is a 2-dimensional polygon with
          four sides, four angles, and four vertices.
        </p>

        <img class="md:p-4 p-4 " src={image} alt="" />
        <p class="p-4">
          <span class="text-2xl font-bold text-blue-600"> Formular </span>
          The area of a rectangle is the product of the breadth and length of a rectangle.
          Therefore, the area of a rectangle formula states that Area of rectangle
          equals Length x Width
        </p>
      </div>

      <!-- <div><h1 class="text-red-600 text-5xl">Triangle</h1></div> -->
      <div class="p-6 md:flex md:flex-row md:items-center">
        <p cclass="p-4">
          <span class="text-2xl font-bold text-red-600"> Definition </span>
          A triangle has six parts, three sides and three angles. Given almost any
          three of them—three sides, two sides and an angle, or one side and two
          angles—you can find the other three values. This is called solving the
          triangle, and you can do it with any triangle, not just a right triangle.
        </p>

        <img class=" md:p-12 py-6" src={image2} alt="" />
        <p class="p-2">
          <span class="text-2xl font-bold text-red-600"> Laws </span>

          For all of this, you need only two tools, the Law of Sines and the Law
          of Cosines. The Law of Sines relates any two sides and the angles
          opposite them, and the Law of Cosines relates all three sides and one
          angle.
        </p>
      </div>

      <!-- <div><h1 class="text-yellow-500 text-5xl">Simple Interest</h1></div> -->
      <div class="p-6 md:flex md:items-center md:justify-center">
        <p class="p-4">
          <span class="text-2xl font-bold text-yellow-500"> Definition </span>
          What Is Simple Interest? Simple interest is a quick and easy method of
          calculating the interest charge on a loan. Simple interest is determined
          by multiplying the daily interest rate by the principal by the number of
          days that elapse between payments.
        </p>

        <img
          class="md:w-96 w-72 p-4 md:items-center md:p-12  "
          src={image3}
          alt=""
        />
        <p class="p-4">
          <span class="text-2xl font-bold text-yellow-500"> Definition </span>

          Understanding Simple Interest When you make a payment on a simple
          interest loan, the payment first goes toward that month’s interest,
          and the remainder goes toward the principal. Each month’s interest is
          paid in full so it never accrues. In contrast, compound interest adds
          some of the monthly interest back onto the loan; in each succeeding
          month, you pay new interest on old interest.
        </p>
      </div>

      <!-- <div><h1 class="text-gray-900 text-5xl">Magic Penny</h1></div> -->
      <div class="p-6 md:flex md:items-center md:justify-center">
        <p class="p-4">
          <span class="text-2xl font-bold text-gray-900">
            HOW DID YOU DO THAT?
          </span>
          For the most part, the resources cited in this article do not explain their
          tricks, because "Magicians never reveal their secrets!" You might choose
          for the tricks to stay in the realm of magic, to intrigue and delight your
          students.
        </p>

        <img class=" md:p-12  md:w-80 w-64 p-4" src={image4} alt="" />
        <p class="p-4">
          <span class="text-2xl md:font-bold text-gray-900">
            BUILT-IN BENEFITS
          </span>

          Many math magic tricks call on students to compute with the four basic
          operations -- sometimes applied to very large numbers. In the context
          of math magic, computational practice is fun.
        </p>
      </div>
    </div>
  </section>
</Animate>
