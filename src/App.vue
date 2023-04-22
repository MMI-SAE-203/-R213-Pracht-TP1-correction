<script setup lang="ts">
import { ref } from 'vue'

const menuIsOpen = ref(false)
</script>

<template>
  <header>
    <h1 class="text-4xl">Test</h1>
    <button
      aria-controls="mainNav"
      :aria-expanded="menuIsOpen"
      class="rounded-full border-2 border-red-600 bg-red-300 px-2"
      @pointerdown="menuIsOpen = !menuIsOpen"
    >
      menu
    </button>
    <!-- nav#mainNav>ul>li*3>a[href="#"]{item $} -->
    <Transition
      class="transition-transform duration-1000"
      enter-from-class="-translate-x-full"
      enter-to-class="translate-x-0"
      leave-active-class="-translate-x-full"
    >
      <nav id="mainNav" v-show="menuIsOpen">
        <ul>
          <li><a href="#">item 1</a></li>
          <li><a href="#">item 2</a></li>
          <li><a href="#">item 3</a></li>
        </ul>
      </nav>
    </Transition>
  </header>

  <main>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tempora recusandae et dolorem odit
      beatae illo labore, praesentium quidem nulla eveniet, at voluptatem incidunt. Eaque explicabo,
      vitae quibusdam vero quod atque.
    </p>
  </main>
</template>
