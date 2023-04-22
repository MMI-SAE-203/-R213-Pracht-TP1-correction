<script setup lang="ts">
import { ref } from 'vue'

const menuIsOpen = ref(false)

const sectionOpen = ref(1)
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
    <!-- section*3>btn.text-xl{bouton $}+p>lorem -->
    <section>
      <button @click="sectionOpen = 1" class="text-xl">bouton 1</button>
      <p v-show="sectionOpen === 1">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Inventore animi dolore, rerum magni
        laudantium quod excepturi laboriosam, ex modi debitis harum reprehenderit eaque quam ut ea
        molestiae. Id, cum dolor!
      </p>
    </section>
    <section>
      <button @click="sectionOpen = 2" class="text-xl">bouton 2</button>
      <p v-show="sectionOpen === 2">
        Amet alias provident quos quis, minus aperiam! Officia ut ab dolores quos dolorem accusamus
        ad, consectetur unde minima, ipsum eligendi inventore id labore, laborum rerum laboriosam
        corrupti iste. Distinctio, perspiciatis!
      </p>
    </section>
    <section>
      <button @click="sectionOpen = 3" class="text-xl">bouton 3</button>
      <p v-show="sectionOpen === 3">
        Repudiandae corporis voluptates, odit reprehenderit sint pariatur at voluptatum, cumque quia
        sit eligendi ex culpa eos, alias magnam molestiae id modi accusantium ipsa eveniet
        accusamus. Tempora quis corporis et nam.
      </p>
    </section>
  </main>
</template>
