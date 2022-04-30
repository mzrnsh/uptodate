---
layout: default
title: "Happy Jekylling!"
---

<div class="py-20 text-center">
  <img
    class="block w-80 mx-auto my-20"
    src="{{ site.baseurl }}/assets/img/logo.svg"
  >

  <div class="relative text-2xl flex justify-center">
    <div>
      Check which
    </div>

    <input
      id="search-input"
      type="text"
      placeholder="
        Ruby on Rails, Font Awesome, Tailwind CSS etc
      "
      class="
        w-60 text-center mx-2 border-b border-gray-300 outline-none
        focus:border-b-2 focus:border-gray-500 placeholder:text-transparent
        relative z-10 peer bg-transparent
      "
      required
    >

    <div
      id="typewriter"
      class="
        absolute top-0 w-full z-0 peer-focus:hidden peer-valid:hidden
        font-extralight text-gray-400
      "
    ></div>

    <div>
      is up to date
    </div>
  </div>
</div>

<div class="text-center">
  This site is not working yet, sorry! 😬
</div>

<script src="https://unpkg.com/typewriter-effect@latest/dist/core.js"></script>
<script>
  new Typewriter('#typewriter', {
    strings: ['Ruby on Rails', 'Font Awesome', 'Tailwind CSS'],
    loop: true,
    autoStart: true
  })
</script>
