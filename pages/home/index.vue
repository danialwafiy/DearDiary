<template>
<div>
    <div class="min-h-screen" :class="color != 'bg-indigo' ? color+'-400':color+'-500'">
        <div class="container pt-12 mx-auto">
            <div class="flex justify-between">
                <div class="flex">
                    <div class="rounded px-4 py-0 bg-red-400 mx-1 border-2 border-white" @click="changeTheme('bg-red')"></div>
                    <div class="rounded px-4 py-0 bg-green-400 mx-1 border-2 border-white" @click="changeTheme('bg-green')"></div>
                    <div class="rounded px-4 py-0 bg-pink-400 mx-1 border-2 border-white" @click="changeTheme('bg-pink')"></div>
                    <div class="rounded px-4 py-0 bg-indigo-500 mx-1 border-2 border-white" @click="changeTheme('bg-indigo')"></div>
                </div>
                <div class="flex justify-between items-center" @click="togglePublic()">
                    <div class="w-12 h-5 flex items-center bg-gray-300 rounded-full  duration-300 ease-in-out" 
                    :class="[(isPublic  && color!='bg-indigo' ? color+'-400 border-2 border-white':''),(isPublic && color=='bg-indigo' ? color+'-500 border-2 border-white':'')]">
                        <div class="bg-white w-7 h-7 rounded-full shadow-md transform duration-300 ease-in-out" 
                        :class="[(isPublic && color!='bg-indigo' ?color+'-400 border-2 border-white translate-x-5':''),(isPublic && color=='bg-indigo' ?color+'-500 border-2 border-white translate-x-5':'')]"></div>
                    </div>
                    <span class="ml-2 text-lg text-white" v-if="isPublic"> <fa :icon="['far','eye']"/> Public</span>
                    <span class="ml-2 text-lg text-white" v-else> <fa :icon="['far','eye-slash']"/> Private</span>
                </div>
                <button class="default-btn bg-white text-gray-500 hover:text-white hover:bg-transparent">
                   <fa :icon="['far','edit']"/> New Secret
                </button>
            </div>
            <div class="-mx-1 flex flex-wrap py-12 justify-center">
                <div class="w-full md:w-1/6 p-1">
                    <div class="bg-white rounded border-4 border-white cursor-pointer" @click="showDiary()">
                        <img class="object-cover h-32 w-full" src="https://tailwindcss.com/img/card-top.jpg" alt="Sunset in the mountains">
                        <div class="px-6 pt-4 pb-1">
                            <div class="font-semibold text-gray-500 text-lg mb-2">The Coldest Sunset</div>
                        </div>
                        <div class="px-6 pb-4">
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['far','calendar-alt']"/> 12/2/2020</span>
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['far','images']"/> 4 Images</span>
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['fas','video']"/> 3 Videos</span>
                        </div>
                    </div>
                </div>
                <div class="w-full md:w-1/6 p-1">
                    <div class="bg-white rounded border-4 border-white cursor-pointer"  @click="showDiary()">
                        <img class="object-cover h-32 w-full" src="https://cdn.cheapism.com/images/011618_most_beautiful_views_in_the_world_sli.max-784x410_ZXOqfVp.jpg" alt="Sunset in the mountains">
                        <div class="px-6 pt-4 pb-1">
                            <div class="font-semibold text-gray-500 text-lg mb-2">The Coldest Sunset</div>
                        </div>
                        <div class="px-6 pb-4">
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['far','calendar-alt']"/> 12/2/2020</span>
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['far','images']"/> 3 Images</span>
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['fas','video']"/> 3 Videos</span>
                        </div>
                    </div>
                </div>                
                <div class="w-full md:w-1/6 p-1">
                    <div class="bg-white rounded border-4 border-white cursor-pointer"  @click="showDiary()">
                        <img class="object-cover h-32 w-full" src="https://cdn.cheapism.com/images/011618_most_beautiful_views_in_the_world_sli.max-784x410_euInqPB.jpg" alt="Sunset in the mountains">
                        <div class="px-6 pt-4 pb-1">
                            <div class="font-semibold text-gray-500 text-lg mb-2">The Coldest Sunset</div>
                        </div>
                        <div class="px-6 pb-4">
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['far','calendar-alt']"/> 12/2/2020</span>
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['far','images']"/> 3 Images</span>
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['fas','video']"/> 3 Videos</span>
                        </div>
                    </div>
                </div>
                <div class="w-full md:w-1/6 p-1">
                    <div class="bg-white rounded border-4 border-white cursor-pointer"  @click="showDiary()">
                        <img class="object-cover h-32 w-full" src="https://i.insider.com/5f15f64c3f7370109a1d96c6?width=1136&format=jpeg" alt="Sunset in the mountains">
                        <div class="px-6 pt-4 pb-1">
                            <div class="font-semibold text-gray-500 text-lg mb-2">The Coldest Sunset</div>
                        </div>
                        <div class="px-6 pb-4">
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['far','calendar-alt']"/> 12/2/2020</span>
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['far','images']"/> 3 Images</span>
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['fas','video']"/> 3 Videos</span>
                        </div>
                    </div>
                </div>
                <div class="w-full md:w-1/6 p-1">
                    <div class="bg-white rounded border-4 border-white cursor-pointer"  @click="showDiary()">
                        <img class="object-cover h-32 w-full" src="https://www.garzablancarealestate.com/blog/wp-content/uploads/2017/09/real-estate-for-vacation-rentals.jpg" alt="Sunset in the mountains">
                        <div class="px-6 pt-4 pb-1">
                            <div class="font-semibold text-gray-500 text-lg mb-2">The Coldest Sunset</div>
                        </div>
                        <div class="px-6 pb-4">
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['far','calendar-alt']"/> 12/2/2020</span>
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['far','images']"/> 3 Images</span>
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['fas','video']"/> 3 Videos</span>
                        </div>
                    </div>
                </div>
                <div class="w-full md:w-1/6 p-1">
                    <div class="bg-white rounded border-4 border-white cursor-pointer"  @click="showDiary()">
                        <img class="object-cover h-32 w-full" src="https://essentialhome.eu/inspirations/wp-content/uploads/2017/06/imagereader-1-1024x682.jpg" alt="Sunset in the mountains">
                        <div class="px-6 pt-4 pb-1">
                            <div class="font-semibold text-gray-500 text-lg mb-2">The Coldest Sunset</div>
                        </div>
                        <div class="px-6 pb-4">
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['far','calendar-alt']"/> 12/2/2020</span>
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['far','images']"/> 3 Images</span>
                            <span class="inline-block bg-gray-500 px-2 py-1 rounded-full text-xs font-semibold text-white mt-1"><fa :icon="['fas','video']"/> 3 Videos</span>
                        </div>
                    </div>  
                </div>
            </div>
        </div>
        <!-- modal -->
        <transition name="fade">
            <div class="flex items-center justify-center fixed left-0 bottom-0 w-full h-full" :class="color != 'bg-indigo' ? color+'-400':color+'-500'"
            v-if="isDiary" 
            @click.self="isDiary=false"
            >
                <div class="bg-white rounded-lg w-1/2">
                    <div class="flex flex-col items-start p-5">
                        <div class="flex items-center w-full">
                            <div class="font-semibold text-gray-600 text-lg">The Coldest Sunset - <small class="text-xs">posted on 12/12/2020</small></div>
                            <svg class="ml-auto fill-current text-gray-700 w-6 h-6 cursor-pointer" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 18 18"
                            @click="isDiary=false"
                            >
                                <path d="M14.53 4.53l-1.06-1.06L9 7.94 4.53 3.47 3.47 4.53 7.94 9l-4.47 4.47 1.06 1.06L9 10.06l4.47 4.47 1.06-1.06L10.06 9z"/>
                            </svg>
                        </div>
                        <div class="flex pt-5">
                            <div class="text-base text-gray-500 text-justify">Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloribus asperiores, vel magni libero exercitationem dolor iste velit consectetur laborum sint aperiam harum eius suscipit animi. Adipisci possimus voluptatibus amet nulla odio quas. Ratione nobis ullam natus maiores aliquam. Mollitia labore dignissimos blanditiis minus pariatur, suscipit ipsum earum rerum nihil aperiam aut repellat nesciunt quaerat ipsa soluta. Ullam cum iusto exercitationem, atque, fugit eos hic, necessitatibus consectetur iure illum quisquam beatae quo delectus? Laborum officia eum eius sed, nam ipsum similique corporis neque soluta asperiores impedit cum atque? Harum culpa consectetur asperiores vitae deserunt reiciendis eum ipsam iste id quasi reprehenderit, est, quia quidem minus iusto aperiam. Delectus, ab illo odit accusamus dolore officiis veritatis, assumenda doloribus, impedit pariatur earum eligendi enim quis sint facere dolores ratione laboriosam? Perferendis doloremque eligendi quasi natus sed eum voluptatem quas omnis at neque molestias necessitatibus, ipsa repellendus incidunt eveniet in, repudiandae, nemo nobis atque.</div>
                        </div>
                        <div class="flex flex-wrap py-5">
                            <div class="w-full md:w-1/4">
                                <img class="object-cover h-32 w-full" src="https://tailwindcss.com/img/card-top.jpg" alt="Sunset in the mountains">
                            </div>                            <div class="w-full md:w-1/4">
                                <img class="object-cover h-32 w-full" src="https://cdn.cheapism.com/images/011618_most_beautiful_views_in_the_world_sli.max-784x410_euInqPB.jpg" alt="Sunset in the mountains">
                            </div>                            <div class="w-full md:w-1/4">
                                <img class="object-cover h-32 w-full" src="https://essentialhome.eu/inspirations/wp-content/uploads/2017/06/imagereader-1-1024x682.jpg" alt="Sunset in the mountains">
                            </div>                            <div class="w-full md:w-1/4">
                                <img class="object-cover h-32 w-full" src="https://cdn.cheapism.com/images/011618_most_beautiful_views_in_the_world_sli.max-784x410_ZXOqfVp.jpg" alt="Sunset in the mountains">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </transition>
    </div>
</div>
</template>

<style>
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>

<script>

export default {

    data(){
        return{
            isDiary:false,
            color: '',
            isPublic: '',
        }
    },
    methods:{
        changeTheme(color){
            if(process.browser){
                localStorage.setItem("theme_color", color);
            }
            this.color = color
        },
        showDiary(){
            this.isDiary = true
        },
        togglePublic(){
            this.isPublic = !this.isPublic
            localStorage.setItem("isPublic", this.isPublic);
        }
    },
    mounted() {
        if(process.browser){
            if(localStorage.getItem("theme_color") === null)
                this.color = 'bg-indigo'
            else
                this.color = localStorage.getItem("theme_color");

            if(localStorage.getItem("isPublic") === null)
                this.isPublic = false
            else
                var bool = localStorage.getItem("isPublic")  == "true" ? true : false
                this.isPublic = bool
                console.log(this.isPublic)
        }
    },
    created() {
        const handleEscape = (e) => {
            if (e.key === 'Esc' || e.key === 'Escape') {
                this.isDiary = false
            }
        }
        if (process.client) {
            document.addEventListener('keydown', handleEscape)
            this.$once('hook:beforeDestroy', () => {
            document.removeEventListener('keydown', handleEscape)
            })
        }
    },
}
</script>
