---
layout: default
title: what?
---

<div class="relative text-2xl flex justify-center font-extralight">
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
      focus:border-gray-500 placeholder:text-transparent
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

<div class="relative">
  <ul
    id="search-results"
    class="
      hidden absolute border rounded-md shadow w-80 mx-auto text-xl
      font-light bg-white z-10 left-0 right-0 -top-px
    "
  >
    {% for product in site.data.products %}
      <li
        data-searchable="true"
        data-handle="{{ product.handle }}"
        data-name="{{ product.name }}"
        class="hidden border-b last:border-b-0 hover:bg-gray-50"
      >
        <a href="/{{ product.handle }}" class="flex justify-between px-4 py-1">
          <span>{{ product.name }}</span>
          <span>{{ product.version }}</span>
        </a>
      </li>
    {% endfor %}
  </ul>
</div>

<script>
  const searchInput = document.getElementById('search-input')
  const searchResults = document.getElementById('search-results')
  const searchables = document.querySelectorAll('[data-searchable]')

  searchInput.addEventListener('input', e => { search(e.target.value) })

  const search = query => {
    query = query.trim()
    if (query.length === 0) return searchResults.classList.add('hidden')

    let resultsCount = 0

    searchables.forEach(searchable => {
      lowerName = searchable.dataset.name.toLowerCase()
      lowerQuery = query.toLowerCase()

      if (lowerName.includes(lowerQuery)) {
        searchable.classList.remove('hidden')
        resultsCount++
      } else {
        searchable.classList.add('hidden')
      }

      if (resultsCount > 0) {
        searchResults.classList.remove('hidden')
      } else {
        searchResults.classList.add('hidden')
      }
    })
  }
</script>

<script src="https://unpkg.com/typewriter-effect@latest/dist/core.js"></script>
<script>
  new Typewriter('#typewriter', {
    strings: ['Ruby on Rails', 'Font Awesome', 'Tailwind CSS'],
    loop: true,
    autoStart: true
  })
</script>
