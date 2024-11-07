<script setup lang="ts">
import { ref } from 'vue'

const posts = ref([
  {
    id: 1,
    title: 'Strength Training',
    description:
      'Lorem ipsum dolor sit amet consectetur adipisicing elit. UllamLorem ipsum dolor sit amet consectetur adipisicing elit. Ullam',
    href: '#',
  },
  {
    id: 2,
    title: 'Physical Fitness',
    description:
      'Lorem ipsum dolor sit amet consectetur adipisicing elit. UllamLorem ipsum dolor sit amet consectetur adipisicing elit. Ullam',
    href: '#',
  },
  {
    id: 3,
    title: 'Fat Lose',
    description:
      'Lorem ipsum dolor sit amet consectetur adipisicing elit. UllamLorem ipsum dolor sit amet consectetur adipisicing elit. Ullam',
    href: '#',
  },
  {
    id: 4,
    title: 'Weight Gain',
    description:
      'Dolor sit amet, consectetur adipiscing elit. Quisque euismod, lorem ac vehicula accumsan, nunc nunc vehicula ipsum.',
    href: '#',
  },
  {
    id: 5,
    title: 'Cardio',
    description:
      'Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid.',
    href: '#',
  },
  {
    id: 6,
    title: 'Yoga',
    description:
      'Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
    href: '#',
  },
])

const icons = ref([
  'src/assets/peso.png',
  'src/assets/forca.png',
  'src/assets/fat.png',
  'src/assets/gain.png',
  'src/assets/cardio.png',
  'src/assets/yoga.png',
])

const visibleIndex = ref(0)

const nextSlide = () => {
  visibleIndex.value = (visibleIndex.value + 3) % posts.value.length
}

const prevSlide = () => {
  visibleIndex.value = (visibleIndex.value - 3 + posts.value.length) % posts.value.length
}
</script>

<template>
  <div class="bg-gradient">
    <header class="h-full">
      <div class="flex items-center justify-between px-6 py-4 container mx-auto">
        <div>
          <img src="@/assets/logo.png" alt="logo" class="w-100" />
        </div>

        <nav class="flex flex-grow justify-center">
          <ul class="flex space-x-6 text-branco mt-5 font-bold">
            <li><a href="#home" class="btn">Home</a></li>
            <li><a href="#about" class="btn">Program</a></li>
            <li><a href="#services" class="btn">Service</a></li>
            <li><a href="#contact" class="btn">About</a></li>
            <li><a href="#community" class="btn">Community</a></li>
          </ul>
        </nav>

        <a href="#dourado" class="goldButton mt-3">Join Now</a>
      </div>

      <div class="flex flex-row w-full h-96 container mx-80 mt-24">
        <div class="w-1/2">
          <div class="letraDourada">BEST FITNESS IN THE TOWN</div>
          <div class="flex flex-row w-full">
            <div class="make w-1/2">MAKE</div>
            <div class="letraBrancaGrande w-1/2">YOUR</div>
          </div>
          <div class="flex flex-row w-full">
            <div class="letraBrancaGrande w-1/2">BODY</div>
            <div class="letraBrancaGrande w-1/2">SHAPE</div>
          </div>

          <div class="text-white mt-4">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Ullam, beatae nulla animi aliquid suscipit ab id
            quam voluptatem, consequuntur laudantium, ducimus et unde. Ex, exercitationem excepturi hic saepe
            reprehenderit dolor.
          </div>

          <button class="goldButton mt-8">Get Started</button>
        </div>

        <div class="flex items-center justify-center w-1/2">
          <img src="@/assets/mem.png" alt="imagem" class="w-full max-w-[300px] h-auto" />
        </div>
      </div>
    </header>
    <div class="flex flex-row justify-between mx-80 mt-40">
      <div class="explore">EXPLORE YOUR PROGRAM</div>
      <div class="flex flex-row">
        <img
          width="50"
          height="50"
          src="@/assets/arrow.svg"
          alt="circled-left-2"
          class="cursor-pointer"
          @click="prevSlide"
        />
        <img
          width="50"
          height="50"
          src="@/assets/arrow2.svg"
          alt="circled-right-2"
          class="cursor-pointer"
          @click="nextSlide"
        />
      </div>
    </div>
    <div class="flex flex-row justify-between mx-80 mt-10">
      <div class="pb-24 w-full">
        <div class="mx-auto max-w-7xl">
          <div
            class="mx-auto mt-10 grid max-w-2xl grid-cols-1 gap-x-8 gap-y-16 border-gray-200 lg:mx-0 lg:max-w-none lg:grid-cols-3"
          >
            <article
              v-for="(post, index) in posts.slice(visibleIndex, visibleIndex + 3)"
              :key="post.id"
              class="flex max-w-xl flex-col items-start justify-between border-2 border-laranja2 rounded-lg"
            >
              <div class="flex items-center gap-x-4 text-xs">
                <img :src="icons[(visibleIndex + index) % icons.length]" alt="icon" />
              </div>
              <div class="group relative">
                <h3 class="mt-3 text-lg/6 font-bold text-branco">
                  <a :href="post.href">
                    <span class="absolute inset-0" />
                    {{ post.title }}
                  </a>
                </h3>
                <p class="mt-5 line-clamp-3 text-sm/6 text-branco">{{ post.description }}</p>
              </div>
              <div class="relative mt-8 flex items-center gap-x-4">
                <button class="goldButton">Join Now</button>
              </div>
            </article>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.explore {
  font-size: 6vh;
  font-weight: 800;
  color: #ffffff;
  text-transform: uppercase;
}

.bg-gradient {
  @apply bg-gradient-to-tr from-cinza1 via-cinza2 to-laranja2;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.letraBrancaGrande {
  font-size: 8vh;
  font-weight: 800;
  color: #ffffff;
  text-transform: uppercase;
}

.make {
  font-size: 8vh;
  font-weight: 800;
  width: 50%;
  text-align: start;
  color: transparent;
  -webkit-text-stroke: 2px #ffffff;
  text-transform: uppercase;
}

.letraDourada {
  color: #f9ac54;
  font-size: x-large;
  font-weight: bold;
}

.btn {
  font-size: 17px;
  background: transparent;
  border: none;
  padding: 1em 1.5em;
  color: #ffffff;
  position: relative;
  transition: 0.5s ease;
  cursor: pointer;
}

.btn::before {
  content: '';
  position: absolute;
  left: 0;
  bottom: 0;
  height: 2px;
  width: 0;
  background-color: #ffc506;
  transition: 0.5s ease;
}

.btn:hover {
  color: #1e1e2b;
  transition-delay: 0.5s;
}

.btn:hover::before {
  width: 100%;
}

.btn::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: 0;
  height: 0;
  width: 100%;
  background-color: #ffc506;
  transition: 0.4s ease;
  z-index: -1;
}

.btn:hover::after {
  height: 100%;
  transition-delay: 0.4s;
  color: aliceblue;
}

.goldButton {
  background-color: #f9ac54;
  color: white;
  border: none;
  padding: 12px 24px;
  font-size: 16px;
  font-weight: bold;
  border-radius: 10px;
  transition:
    background-color 0.3s ease,
    transform 0.3s ease;
  cursor: pointer;
}
</style>
