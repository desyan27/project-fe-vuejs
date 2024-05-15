<template>
    <nav class="bg-white w-full top-0 z-20">
        <div class="items-center px-4 max-w-screen-xl mx-auto lg:flex lg:px-8">
            <div class="flex items-center justify-between py-3 lg:py-4 lg:block">
                <div class="flex items-center ms-4 my-4 max-w-lg">
                    <a href="javascript:void(0)">
                        <img src="/src/assets/Emporio.png" width="120" height="50" alt="Emporio" />
                    </a>
                    <div class="relative ms-6">
                        <div class="absolute inset-y-0 end-0 flex items-center pointer-events-none me-2">
                            <svg class="w-4 h-4 text-gray-500 dark:text-gray-400" aria-hidden="true"
                                xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 20 20">
                                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
                                    stroke-width="2" d="m19 19-4-4m0-7A7 7 0 1 1 1 8a7 7 0 0 1 14 0Z" />
                            </svg>
                        </div>
                        <input type="text"
                            class="w-full p-2 text-sm text-gray-900 border border-gray-300 rounded-lg bg-slate-100 focus:ring-blue-500 focus:border-blue-500"
                            placeholder="Search" required />
                    </div>
                </div>
                <div class="lg:hidden">
                    <button class="text-gray-700 outline-none p-2 rounded-md focus:border-gray-400 focus:border"
                        @click="menuOpen()">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" viewBox="0 0 20 20" fill="currentColor"
                            :class="[open ? 'block' : 'hidden']">
                            <path fillRule="evenodd"
                                d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                                clipRule="evenodd" />
                        </svg>
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24"
                            :class="[open ? 'hidden' : 'block']" stroke="currentColor">
                            <path strokeLinecap="round" strokeLinejoin="round" strokeWidth="2" d="M4 8h16M4 16h16" />
                        </svg>
                    </button>
                </div>
            </div>

            <div class="flex-1 justify-between flex-row-reverse lg:overflow-visible lg:flex lg:pb-0 lg:pr-0 lg:h-auto"
                :class="[open ? 'h-screen pb-20 overflow-auto pr-4' : 'hidden']">
                <div>
                    <ul class="flex flex-col-reverse space-x-0 lg:space-x-6 lg:flex-row">
                        <li class="mt-4 lg:mt-0">
                            <a href="javascript:void(0)"
                                class="py-3 px-4 text-center border text-zinc-950 hover:text-zinc-500 font-semibold rounded-md block lg:inline lg:border-0">
                                Login
                            </a>
                        </li>
                        <li class="mt-8 lg:mt-0">
                            <a href="javascript:void(0)"
                                class="py-3 px-4 text-center text-white font-semibold bg-zinc-950 hover:bg-zinc-600 rounded-md shadow block lg:inline">
                                Sign Up
                            </a>
                        </li>
                    </ul>
                </div>
                <div class="flex-1 mr-4">
                    <ul class="justify-end items-center space-y-8 lg:flex lg:space-x-6 lg:space-y-0">
                        <li v-for="link in navigation" :key="link.id"
                            class="text-zinc-950 hover:text-zinc-500 font-semibold">
                            <a :href="link.router">
                                {{ link.title }}
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </nav>
</template>

<style scoped>
.sticky-nav {
    animation: sticky-nav 300ms;
}

@keyframes sticky-nav {
    0% {
        transform: translateY(-6em)
    }

    100% {
        transform: translateY(0)
    }
}
</style>

<script>
import { ref } from 'vue';
export default {
    name: 'Navbar',
    data: function () {
        return {
            navigation: [
                { title: "New Products", router: "/NewProducts" },
                { title: "Men", router: "/Men" },
                { title: "Women", router: "/Women" },
            ]
        }
    },
    setup() {
        let open = ref(false);
        function menuOpen() {
            open.value = !open.value;
        }
        return { open, menuOpen };
    },

}
</script>