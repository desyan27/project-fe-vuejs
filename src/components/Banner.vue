<template>
    <div class="bg-lime-400 items-center w-full grid-cols-2 mx-auto overflow-x-hidden lg:grid md:py-14 lg:py-24 xl:py-14 lg:mt-3"
        data-aos="fade-right" data-aos-duration="800">
        <div class="pr-2 md:mb-14 py-14 md:py-0 my-6">
            <div class="flex justify-center items-center">\
                <img src="/src/assets/text.png" alt="Start Your Day With A Fresh New Look" class="w-full sm:w-4/6">
            </div>
            <div class="my-6 flex justify-center items-center">
                <a href="#"class="px-5 py-3 text-lg tracking-wider text-white font-bold bg-blue-500 rounded-lg md:px-8 hover:bg-blue-600 group">
                    <span>Shop Now</span> 
                </a>
            </div>
        </div>
        <div class="pb-10 overflow-hidden md:p-10 lg:p-0 sm:pb-0">
            <img id="heroImg1"
                class="transition-all duration-300 ease-in-out hover:scale-110 lg:w-1/2 sm:mx-auto sm:w-full sm:pb-12 lg:pb-0"
                src="/src/assets/man.png" alt="Awesome hero page image" width="500" height="488" />
        </div>
    </div>
</template>
<script>
export default {
    name: 'Banner'
}
</script>