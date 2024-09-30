<template >
    <section class="text-white mt-20" id="testimonials" data-aos="zoom-in">
        <h2 class="text-4xl font-bold text-white text-left mb-4 px-4 xl:pl-16">Testimonials</h2>
        <div class="px-4 xl:px-16">
            <Carousel v-bind="settings" :breakpoints="breakpoints" >
                <Slide v-for="element in testimonials" :key="element.id">
                    <div class="carousel__item p-4">
                        <div class="w-full mx-auto bg-[#111a3e] shadow-lg border border-[#1f1641] p-5 text-white font-light mb-6">
                            <div class="w-full flex mb-4 items-center">
                                <div class="overflow-hidden rounded-full w-10 h-10 bg-gray-50 border border-gray-200">
                                    <img :src="element.image" alt="testimonial image" loading="lazy">
                                </div>
                                <h6 class="ml-4 font-bold text-sm uppercase text-white">{{ element.fullName }}</h6>
                            </div>
                            <div class="w-full">
                                <p class="text-sm leading-tight">
                                    <span class="text-lg leading-none italic font-bold text-white mr-1">"</span>
                                        {{ element.comment }}
                                    <span class="text-lg leading-none italic font-bold text-white mr-1">"</span>
                                </p>
                            </div>
                        </div>
                    </div>
                </Slide> 
                <template #addons>
                    <Navigation />
                </template>
            </Carousel>
        </div>
    </section>
</template>
<script setup>
import { ref } from 'vue';
import { Carousel , Navigation , Slide } from 'vue3-carousel';
import 'vue3-carousel/dist/carousel.css';
//Carousel settings
const settings =ref({
    itemsToShow:1,
    snapAlign:"center",
})

//Breakpoints
const breakpoints =ref({
    700:{
        itemsToShow:2.5,
        snapAlign:'center',
    },
    1024:{
        itemsToShow:3,
        snapAlign:'start'
    }
})

const testimonials=ref([
    {
        id:1,
        fullName:'Tara Chand',
        image:'src/assets/tara.jpg  ',
        comment:'As a dedicated developer, I pride myself on delivering high-quality projects that meet my clients needs. Here are some highlights of my recent client work'
    },
    {
        id:2,
        fullName:'Vijay Kumar',
        image:'src/assets/vijay.enc',
        comment:'We are thrilled with the website developed by [Rahul Yadav]. The design is not only visually stunning but also highly functional. The user experience has significantly improved, and our visitors have commented on how easy it is to navigate. [Your Name] was professional, responsive, and delivered the project ahead of schedule. We highly recommend their services to anyone looking for quality web development!"'
    },
    {
        id:4,
        fullName:'Rahul',
        image:'src/assets/iop.jpeg',
        comment:'Thanks to [Rahul Yadav], our website looks amazing! The responsiveness and speed are impressive, and the SEO improvements have already started to pay off. Their professionalism and expertise made the whole process smooth and enjoyable.'
    },
    {
        id:3,
        fullName:'Dharmesh Yadav',
        image:'src/assets/poi.jpeg',
        comment:'Working with [Rahul Yadav] was a fantastic experience. They took the time to understand our brand and tailored the website to reflect our identity perfectly. The project was completed on time and with exceptional attention to detail."'
    },
    {
        id:5,
        fullName:'Amit Yadav',
        image:'src/assets/image.png',
        comment:'The website exceeded our expectations! [Rahul Yadav] brought our vision to life with a beautiful design and seamless functionality. The feedback from our users has been overwhelmingly positive, and we’ve seen an increase in traffic and engagement since the launch.'
    },
])
</script>
<style >
    .carousel__prev,.carousel__next {
        color: white !important;
    }
</style>