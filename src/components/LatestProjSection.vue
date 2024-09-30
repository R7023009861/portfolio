<template>
    <section class="text-white mt-20" id="projects">
        <div class="px-4 xl:pl-16">
            <div class="mb-4 md:flex md:justify-between xl:pr-16">
                <h2 class="text-4xl font-bold text-white"> My Latest Projects</h2>
                <div class="flex space-x-4 mb-4 mt-5 md:mt-0">
                    <button class="hover:text-primary" v-for="category in ['All', 'Web Development', 'Mobile App']"
                        :key="category" @click="() => selectedCategory = category">
                        {{ category }}
                    </button>
                </div>
            </div>
            <ul class="px-4 sm:py-16 xl:pr-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3"
                data-aos="fade-right">
                <div v-for="project in filteredProjects" :key="project.id">
                    <div class="h-52 md:h-[24rem] rounded-t-xl relative group"
                    :style="{ backgroundImage: 'url(' + project.image + ')', backgroundSize: 'cover' }">                    
                    <div class="overlay items-center justify-center absolute top-0 left-0 w-full h-full bg-[#181818] bg-opacity-0
                    hidden group-hover:flex group-hover:bg-opacity-80 transition-all duration-500
                    ">
                        <a class="h-14 w-14 mr-2 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link"
                            :href="project.webURL"> <svg xmlns="http://www.w3.org/2000/svg" fill="none"
                                viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true"
                                data-slot="icon"
                                class="h-10 w-10 text-[#ADB7BE] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2  cursor-pointer group-hover/link:text-white">
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M17.25 6.75 22.5 12l-5.25 5.25m-10.5 0L1.5 12l5.25-5.25m7.5-3-4.5 16.5">
                                </path>
                            </svg></a><a
                            class="h-14 w-14 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link"
                            :href="project.gitURL"> <svg xmlns="http://www.w3.org/2000/svg" fill="none"
                                viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true"
                                data-slot="icon"
                                class="h-10 w-10 text-[#ADB7BE] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2  cursor-pointer group-hover/link:text-white">
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M2.036 12.322a1.012 1.012 0 0 1 0-.639C3.423 7.51 7.36 4.5 12 4.5c4.638 0 8.573 3.007 9.963 7.178.07.207.07.431 0 .639C20.577 16.49 16.64 19.5 12 19.5c-4.638 0-8.573-3.007-9.963-7.178Z">
                                </path>
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z"></path>
                            </svg></a>
                    </div>
                </div>
                <div class="text-white rounded-b-xl mt-3 bg-[#111a3e] shadow-lg border border-[#1f1641] py-6 px-4">
                    <h3 class="text-lg font-semibold uppercase lg:text-xl"> {{ project.title }}</h3>
                    <p class="text-[#ADB7BE]">{{ project.description }}</p>
                    <div class="flex flex-wrap p-2.5">
                        <div v-for="technology in project.technologies" :key="technology" class="text-center ml-1 mt-1 rounded-3xl bg-[#111827]"
                        style="box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1); border: 1px solid #111827;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);"
                        >
                    <p class="px-1 py-2">{{ technology }}</p>
                    </div>
                    </div>
                </div>
                </div>
            </ul>
        </div>
    </section>
</template>
<script setup>
import { ref, computed } from 'vue';

const Projects = ref([
    {
        id: 1,
        category: 'web development',
        image: 'src/assets/todo.avif',
        title: 'To-Do App',
        description: 'The To-Do List App is a simple and intuitive task management tool designed to help users organize their daily activities efficiently. With a user-friendly interface, this app allows users to create, manage, and track their tasks in a seamless manner.',
        technologies: ['HTML','CSS','JAVASCRIPT'],
        gitURL: 'https://github.com/R7023009861/Calculater.git',
        webURL: ''
    },
    {
        id: 2,
        category: 'Mobile App',
        image: 'src/assets/calculater.webp',
        title: 'Calculater',
        description: 'The Calculator App is a versatile and user-friendly tool designed to perform a variety of mathematical operations with ease. Whether for basic arithmetic or more advanced calculations, this app offers a sleek and intuitive interface to meet all your calculating needs.',
        technologies: ['HTML','CSS','JAVASCRIPT'],
        gitURL: 'https://github.com/R7023009861/Calculater.git',
        webURL: ''
    },
    {
        id: 3,
        category: 'web design',
        image: 'src/assets/ert.avif',
        title: 'E-commerce site',
        description: 'The E-Commerce Website is a comprehensive online shopping platform designed to provide users with a seamless and enjoyable shopping experience. Featuring a wide range of products, user-friendly navigation, and secure payment options, this site aims to meet the needs of modern consumers.',
        technologies: ['HTML','CSS','JAVASCRIPT'],
        gitURL: 'https://github.com/R7023009861/Calculater.git',
        webURL: ''
    },
    {
        id: 4,
        category: 'Mobile App',
        image: 'src/assets/tictaktoe.webp',
        title: 'Tic-Tak-Toe Game',
        description: 'Dive into the classic game of Tic Tac Toe with our intuitive and engaging app! Perfect for players of all ages, our app offers a seamless experience with a clean design and easy-to-use interface. Challenge your friends in multiplayer mode or test your skills against our smart AI in single-player mode.',
        technologies: ['HTML','CSS','JAVASCRIPT'],
        gitURL: 'https://github.com/R7023009861/Calculater.git',
        webURL: ''
    }
    // {
    //     id: 5,
    //     category: 'web development',
    //     image: 'src/assets/project.png',
    //     title: 'project 1',
    //     description: 'This project is a web design initiative aimed at [briefly describe the main purpose of your project, e.g., "creating a visually appealing portfolio site," "developing a user-friendly e-commerce platform," etc.]. The goal was to blend aesthetics with functionality to enhance user engagement and accessibility.',
    //     technologies: ['vue.js 3', 'vuex', 'Express'],
    //     gitURL: 'https://github.com/R7023009861/Calculater.git',
    //     webURL: ''
    // },
    // {
    //     id: 6,
    //     category: 'Mobile App',
    //     image: 'src/assets/mobile.jpg',
    //     title: 'project 1',
    //     description: 'This project is a web design initiative aimed at [briefly describe the main purpose of your project, e.g., "creating a visually appealing portfolio site," "developing a user-friendly e-commerce platform," etc.]. The goal was to blend aesthetics with functionality to enhance user engagement and accessibility.',
    //     technologies: ['vue.js 3', 'vuex', 'Express'],
    //     gitURL: 'https://github.com/R7023009861/Calculater.git',
    //     webURL: ''
    // }
]);

const selectedCategory = ref('all');
const filteredProjects = computed(() => {
    if (selectedCategory.value === 'all') {
        return Projects.value;
    }
    return Projects.value.filter(project => project.category.toLocaleLowerCase() === selectedCategory.value.toLocaleLowerCase());
})

</script>