<template>
    <div class="h-screen flex">
        <div class="flex w-1/2 bg-login bg-cover i justify-around items-center">
            <div v-if="!readMore" class="animate__bounceIn">
                <h1 class=" text-white font-bold text-4xl font-sans mb-4">Welcome to Chiak</h1>
                <p class="text-white mt-1">Your favourite dietary companion.</p>
                <button @click="toggleReadMore()" type="submit" class="block w-28 bg-white text-indigo-800 mt-4 py-2 rounded-2xl font-bold mb-2">Read More</button>
            </div>
            <div v-else class="animate__bounceIn">
                <h1 class=" text-white font-bold text-4xl font-sans mb-4">Who are we?</h1>
                <p class="text-white mt-1">We are a team of passionate individuals who want to<br> encourage healthier lifestyles by easing one step of the <br>process. This is just the beginning!</p>
                <button @click="toggleReadMore()" type="submit" class="block w-28 bg-white text-indigo-800 mt-4 py-2 rounded-2xl font-bold mb-2">Back</button>
            </div>
        </div>
        <div class="flex w-1/2 justify-center items-center bg-white">
            <form class="bg-white">
            <h1 class="text-gray-800 font-bold text-2xl mb-7">Enter your email, we'll <br> send you a new password.</h1>
            <div class="flex items-center border-2 py-2 px-3 rounded-2xl mb-7">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 12a4 4 0 10-8 0 4 4 0 008 0zm0 0v1.5a2.5 2.5 0 005 0V12a9 9 0 10-9 9m4.5-1.206a8.959 8.959 0 01-4.5 1.207" />
                </svg>
                <input class="pl-2 outline-none border-none" type="email" name="" id="" placeholder="Email Address" />
            </div>
            <button type="submit" class="block w-full bg-green-600 mt-4 py-2 rounded-2xl text-white font-semibold mb-3">Login</button>
            <span @click='login()' class="text-sm ml-2 hover:text-green-500 cursor-pointer">Back to Login</span><br><br>
            </form>
        </div>
    </div>
</template>
<script>
export default {
    name: "ForgotPassword",
    props: {

    },
    data () {
        return {
            readMore: false
        }
    },
    methods: {
        login() {
            this.$router.push('/login')
        },
        toggleReadMore(){
            this.readMore = !this.readMore
        }
    }
}
</script>
<style>
    
</style>