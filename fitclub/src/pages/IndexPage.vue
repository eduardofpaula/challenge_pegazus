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
          <img src="@/assets/logo.png" alt="logo" class="w-32 sm:w-40 md:w-48" />
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

      <div class="flex flex-wrap h-96 container mr-10 mx-auto mt-24 px-6">
        <div class="w-full sm:w-1/2 mb-6 sm:mb-0">
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

        <div class="flex items-center justify-center w-full sm:w-1/2">
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

    <div class="flex flex-row container ml-60 mt-10">
      <div class="w-1/2 relative h-full mr-20">
        <img class="absolute ps-44" src="../assets/ropeMen.jpg" alt="men2" />
        <img class="absolute mt-80" src="../assets/bustMen.jpg" alt="men1" />
      </div>
      <div class="w-1/2 h-full pb-80">
        <div class="letraBrancaGrande">THE CLASS YOU WILL GET HERE</div>
        <div class="text-white mt-4">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Ullam, beatae nulla animi aliquid suscipit ab id quam
          voluptatem, consequuntur laudantium, ducimus et unde. Ex, exercitationem excepturi hic saepe reprehenderit
          dolor.
        </div>
        <div>
          <button class="goldButton mt-8">Book a Class</button>
        </div>
      </div>
    </div>
    <footer class="container mx-auto mt-10 grid grid-cols-4 gap-8 px-8 py-10 bg-gray-900 text-white">
      <div>
        <img src="@/assets/logo.png" alt="Logo da Empresa" class="w-32 sm:w-40 md:w-48" />
        <p class="pt-4 text-gray-400">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Non dolore hic molestiae, tempore quaerat quam cumque
          ipsum maxime cum dolorum!
        </p>

        <ul class="social">
          <li class="icon facebook">
            <span class="tooltip">Facebook</span>
            <svg viewBox="0 0 320 512" height="1.2em" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M279.14 288l14.22-92.66h-88.91v-60.13c0-25.35 12.42-50.06 52.24-50.06h40.42V6.26S260.43 0 225.36 0c-73.22 0-121.08 44.38-121.08 124.72v70.62H22.89V288h81.39v224h100.17V288z"
              ></path>
            </svg>
          </li>
          <li class="icon twitter">
            <span class="tooltip">Twitter</span>
            <svg
              height="1.8em"
              fill="currentColor"
              viewBox="0 0 48 48"
              xmlns="http://www.w3.org/2000/svg"
              class="twitter"
            >
              <path
                d="M42,12.429c-1.323,0.586-2.746,0.977-4.247,1.162c1.526-0.906,2.7-2.351,3.251-4.058c-1.428,0.837-3.01,1.452-4.693,1.776C34.967,9.884,33.05,9,30.926,9c-4.08,0-7.387,3.278-7.387,7.32c0,0.572,0.067,1.129,0.193,1.67c-6.138-0.308-11.582-3.226-15.224-7.654c-0.64,1.082-1,2.349-1,3.686c0,2.541,1.301,4.778,3.285,6.096c-1.211-0.037-2.351-0.374-3.349-0.914c0,0.022,0,0.055,0,0.086c0,3.551,2.547,6.508,5.923,7.181c-0.617,0.169-1.269,0.263-1.941,0.263c-0.477,0-0.942-0.054-1.392-0.135c0.94,2.902,3.667,5.023,6.898,5.086c-2.528,1.96-5.712,3.134-9.174,3.134c-0.598,0-1.183-0.034-1.761-0.104C9.268,36.786,13.152,38,17.321,38c13.585,0,21.017-11.156,21.017-20.834c0-0.317-0.01-0.633-0.025-0.945C39.763,15.197,41.013,13.905,42,12.429"
              ></path>
            </svg>
          </li>
          <li class="icon instagram">
            <span class="tooltip">Instagram</span>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              height="1.2em"
              fill="currentColor"
              class="bi bi-instagram"
              viewBox="0 0 16 16"
            >
              <path
                d="M8 0C5.829 0 5.556.01 4.703.048 3.85.088 3.269.222 2.76.42a3.917 3.917 0 0 0-1.417.923A3.927 3.927 0 0 0 .42 2.76C.222 3.268.087 3.85.048 4.7.01 5.555 0 5.827 0 8.001c0 2.172.01 2.444.048 3.297.04.852.174 1.433.372 1.942.205.526.478.972.923 1.417.444.445.89.719 1.416.923.51.198 1.09.333 1.942.372C5.555 15.99 5.827 16 8 16s2.444-.01 3.298-.048c.851-.04 1.434-.174 1.943-.372a3.916 3.916 0 0 0 1.416-.923c.445-.445.718-.891.923-1.417.197-.509.332-1.09.372-1.942C15.99 10.445 16 10.173 16 8s-.01-2.445-.048-3.299c-.04-.851-.175-1.433-.372-1.941a3.926 3.926 0 0 0-.923-1.417A3.911 3.911 0 0 0 13.24.42c-.51-.198-1.092-.333-1.943-.372C10.443.01 10.172 0 7.998 0h.003zm-.717 1.442h.718c2.136 0 2.389.007 3.232.046.78.035 1.204.166 1.486.275.373.145.64.319.92.599.28.28.453.546.598.92.11.281.24.705.275 1.485.039.843.047 1.096.047 3.231s-.008 2.389-.047 3.232c-.035.78-.166 1.203-.275 1.485a2.47 2.47 0 0 1-.599.919c-.28.28-.546.453-.92.598-.28.11-.704.24-1.485.276-.843.038-1.096.047-3.232.047s-2.39-.009-3.233-.047c-.78-.036-1.203-.166-1.485-.276a2.478 2.478 0 0 1-.92-.598 2.48 2.48 0 0 1-.6-.92c-.109-.281-.24-.705-.275-1.485-.038-.843-.046-1.096-.046-3.233 0-2.136.008-2.388.046-3.231.036-.78.166-1.204.276-1.486.145-.373.319-.64.599-.92.28-.28.546-.453.92-.598.282-.11.705-.24 1.485-.276.738-.034 1.024-.044 2.515-.045v.002zm4.988 1.328a.96.96 0 1 0 0 1.92.96.96 0 0 0 0-1.92zm-4.27 1.122a4.109 4.109 0 1 0 0 8.217 4.109 4.109 0 0 0 0-8.217zm0 1.441a2.667 2.667 0 1 1 0 5.334 2.667 2.667 0 0 1 0-5.334z"
              ></path>
            </svg>
          </li>
        </ul>
      </div>
      <nav>
        <h3 class="cabecalho">Company</h3>
        <ul>
          <li>Business</li>
          <li>Franchise</li>
          <li>Partnership</li>
          <li>Network</li>
        </ul>
      </nav>

      <nav>
        <h3 class="cabecalho">About Us</h3>
        <ul>
          <li>Blogs</li>
          <li>Security</li>
          <li>Careers</li>
        </ul>
      </nav>
      <nav>
        <h3 class="cabecalho">Contact</h3>
        <ul>
          <li>Contact Us</li>
          <li>Privacy Policy</li>
          <li>Forms & Conditions</li>
          <li>BMI Calculator</li>
        </ul>
      </nav>
    </footer>
  </div>
</template>

<style scoped>
.cabecalho {
  font-weight: 600;
  font-size: 1.125rem;
  line-height: 1.75rem;
  color: #ffffff;
  margin-bottom: 0.5rem;
  margin-bottom: 0.5rem;
}
.cabecalho + ul > li {
  --tw-space-y-reverse: 0;
  margin-top: calc(0.5rem /* 8px */ * calc(1 - var(--tw-space-y-reverse)));
  margin-bottom: calc(0.5rem /* 8px */ * var(--tw-space-y-reverse));
  color: #9ca3af;
  --tw-text-opacity: 1;
  color: rgb(156 163 175 / var(--tw-text-opacity));
}

.social {
  display: inline-flex;
  list-style: none;
  padding-top: 20px;
  font-family: 'Poppins', sans-serif;
  justify-content: center;
}

.social .icon {
  position: relative;
  background: #f9ac54;
  border-radius: 50%;
  margin: 10px;
  width: 50px;
  height: 50px;
  font-size: 18px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  box-shadow: 0 10px 10px rgba(0, 0, 0, 0.1);
  cursor: pointer;
  transition: all 0.2s cubic-bezier(0.68, -0.55, 0.265, 1.55);
}

.social .tooltip {
  position: absolute;
  top: 0;
  font-size: 14px;
  background: #f9ac54;
  color: #fff;
  padding: 5px 8px;
  border-radius: 5px;
  box-shadow: 0 10px 10px rgba(0, 0, 0, 0.1);
  opacity: 0;
  pointer-events: none;
  transition: all 0.3s cubic-bezier(0.68, -0.55, 0.265, 1.55);
}

.social .tooltip::before {
  position: absolute;
  content: '';
  height: 8px;
  width: 8px;
  background: #f9ac54;
  bottom: -3px;
  left: 50%;
  transform: translate(-50%) rotate(45deg);
  transition: all 0.3s cubic-bezier(0.68, -0.55, 0.265, 1.55);
}

.social .icon:hover .tooltip {
  top: -45px;
  opacity: 1;
  visibility: visible;
  pointer-events: auto;
}

.social .icon:hover span,
.social .icon:hover .tooltip {
  text-shadow: 0px -1px 0px rgba(0, 0, 0, 0.1);
}

.social .facebook:hover,
.social .facebook:hover .tooltip,
.social .facebook:hover .tooltip::before {
  background: #f9ac54;
  color: #fff;
}

.social .twitter:hover,
.social .twitter:hover .tooltip,
.social .twitter:hover .tooltip::before {
  background: #f9ac54;
  color: #fff;
}

.social .instagram:hover,
.social .instagram:hover .tooltip,
.social .instagram:hover .tooltip::before {
  background: #f9ac54;
  color: #fff;
}

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
