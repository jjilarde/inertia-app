<script setup>
import { onMounted } from "vue";
import { Link } from "@inertiajs/vue3";
import { initFlowbite } from "flowbite";

onMounted(() => {
    initFlowbite();
});

const navLinks = [
    { name: "Home", href: route("home") },
    { name: "About", href: route("about") },
    { name: "Services", href: route("services") },
    { name: "Pages", href: route("pages") },
    { name: "Blog", href: route("blog") },
    { name: "Contact", href: route("contact") },
];
</script>
<template>
    <nav class="overflow-x-auto flex pl-36 mx-auto bg-white">
        <div class="flex">
            <Link :href="route('dashboard')">
                <img src="images/tailwind.png" class="h-24 w-40 cursor-pointer" alt="" />
            </Link>        </div>
        <div class="flex justify-center items-center space-x-16 mx-auto">
            <div v-for="link in navLinks" :key="link.name">
                <Link
                    :href="link.href"
                    :class="$page.url === link.href ? 'text-blue-800' : '' "
                    class="font-semibold hover:text-blue-800 focus:text-blue-800"
                >
                    {{ link.name }}
                </Link>
            </div>
            <div class="flex justify-items-center space-x-12 pl-48">
                <div class="flex justify-center items-center pt-4">
                    <div
                        class="relative mb-4 flex w-full flex-wrap items-stretch"
                    >
                        <input
                            type="search"
                            class="md:flex-shrink-0 block relative m-0 min-w-0 flex-auto rounded border border-solid border-neutral-300 bg-transparent bg-clip-padding px-3 py-[0.25rem] text-base font-normal leading-[1.6] text-neutral-700 outline-none transition duration-200 ease-in-out focus:z-[3] focus:border-primary focus:text-neutral-700 focus:shadow-[inset_0_0_0_1px_rgb(59,113,202)] focus:outline-none dark:border-neutral-600 dark:text-neutral-200 dark:placeholder:text-neutral-200 dark:focus:border-primary"
                            placeholder="Search"
                            aria-label="Search"
                            aria-describedby="button-addon2"
                        />

                        <span
                            class="hidden md:block sm:block input-group-text items-center whitespace-nowrap rounded px-3 py-1.5 text-center text-base font-normal text-neutral-700 dark:text-neutral-200"
                            id="basic-addon2"
                        >
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                viewBox="0 0 20 20"
                                fill="currentColor"
                                class="h-5 w-5"
                            >
                                <path
                                    fill-rule="evenodd"
                                    d="M9 3.5a5.5 5.5 0 100 11 5.5 5.5 0 000-11zM2 9a7 7 0 1112.452 4.391l3.328 3.329a.75.75 0 11-1.06 1.06l-3.329-3.328A7 7 0 012 9z"
                                    clip-rule="evenodd"
                                />
                            </svg>
                        </span>
                    </div>
                </div>
                <div class="flex items-center">
                    <button
                        type="button"
                        class="flex rounded-sm bg-blue-800 px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-blue-600 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-blue-800"
                    >
                        Get A Quote
                    </button>
                </div>
            </div>
        </div>
    </nav>
</template>
