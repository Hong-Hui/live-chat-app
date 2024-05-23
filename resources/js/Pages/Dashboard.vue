<script setup lang="ts">
import { ref } from 'vue';
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head } from "@inertiajs/vue3";

// const props = defineProps<{
//   chatRoomTabs?: array,
// }>();

const chatRoomTabs = ref([
    { id: 1, image: 'https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/1235.jpg', name: "first room" },
    { id: 2, image: 'https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/1230.jpg', name: "second room" },
    { id: 3, image: 'https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/1036.jpg', name: "third room" },
    { id: 4, image: 'https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/1012.jpg', name: "fourth room" },
    { id: 5, image: 'https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/995.jpg', name: "fifth room" },
]);

const messages = ref([
    { id: 1, body: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Hic, beatae!' },
    { id: 2, body: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. At dolore eum, facilis quo esse totam a modi consectetur vero inventore quae itaque dolorum incidunt aspernatur vitae ad sapiente sunt culpa!' },
    { id: 3, body: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Facere, numquam deleniti sit aut cumque animi ullam.' },
])
</script>
<template>

    <Head title="Dashboard" />
    <AuthenticatedLayout>
        <div class="py-10">
            <div class="flex flex-row items-start justify-center gap-5 mx-auto sm:px-6 lg:px-10">
                <!-- /* ----------------------------- chat room tabs ----------------------------- */ -->
                <div
                    class="overflow-hidden bg-white shadow-sm dark:bg-gray-800 sm:rounded-lg min-w-[350px] p-5 flex flex-col gap-5 border border-slate-200">
                    <div
                        class="p-2 text-sm font-semibold tracking-wide text-center text-gray-900 border rounded-xl dark:text-gray-100 border-slate-200">
                        Chat Rooms </div>
                    <ul class="flex flex-col gap-2.5">
                        <li v-for="chatRoomTab in chatRoomTabs" :key="chatRoomTab.id">
                            <div
                                class="cursor-pointer hover:shadow-md duration-300 flex flex-row items-center gap-5 px-5 py-2.5 border rounded-xl shadow-sm border-slate-200">
                                <div class="flex items-center justify-center overflow-hidden rounded-full size-16 bg-slate-400">
                                    <img :src="chatRoomTab.image" alt="chat-room-image" class="object-cover size-full" aria-hidden="true">
                                </div>
                                <div class="flex-col gap-2.5 flex">
                                    <span class="text-sm font-medium capitalize">{{ chatRoomTab.name }}</span>
                                    <span class="text-sm capitalize">test</span>
                                </div>
                            </div>
                        </li>
                    </ul>
                </div>
                <!-- /* --------------------------- chat room messages --------------------------- */ -->
                <div
                    class="flex flex-col w-full max-w-3xl gap-5 p-5 overflow-hidden bg-white border shadow-sm dark:bg-gray-800 sm:rounded-lg border-slate-200">
                    <div
                        class="p-2 text-sm font-semibold tracking-wide text-center text-gray-900 border rounded-xl dark:text-gray-100 border-slate-200">
                        Chat Room Messages </div>
                    <ul class="flex flex-col gap-10">
                        <li v-for="message in messages" :key="message.id">
                            <div class="flex flex-row items-start gap-5">
                                <div class="flex items-center justify-center rounded-full size-14 bg-slate-400">image</div>
                                <div class="text-balance max-w-md px-5 py-2.5 rounded-xl bg-slate-200 text-sm tracking-wide leading-6">{{ message.body
                                    }}</div>
                            </div>
                        </li>
                        <li>
                            <div class="flex flex-row-reverse items-start gap-5">
                                <div class="flex items-center justify-center rounded-full size-14 bg-slate-400">image</div>
                                <div class="text-balance max-w-md px-5 py-2.5 rounded-xl bg-slate-200 text-sm tracking-wide leading-6">Lorem, ipsum
                                    dolor sit amet consectetur adipisicing elit. Nisi eos, ut quam consequuntur ipsum inventore quasi, eligendi,
                                    blanditiis unde deleniti quisquam officia eius voluptas molestias reprehenderit earum omnis illo fugiat!</div>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
